# Creating Container Challenges
Container challenges are the most complex, but they are also among the most impactful features of our platform. To get started, we will build a Docker container on our local machine and later use it on our platform. We will need Docker installed and a Docker Hub account to which we can push our container.

Note: All containers must be publicly available on Docker Hub.

## Creating the container

Create a new folder on your machine called `seclabs`. Inside that folder, create another folder called `html`. In this `html` folder, create a new `index.html` file with the following contents:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <title>Hello seclabs!</title>
  </head>

  <body>
    <h1>Welcome to our container</h1>
    <p>here is your flag: {FLAG1}</p>
  </body>
</html>
```

Add a `Dockerfile` to the `seclabs` folder with the following contents:

```dockerfile
FROM nginx

COPY ./html/ /usr/share/nginx/html/

COPY ./entrypoint.sh /usr/local/bin/entrypoint.sh
RUN chmod +x /usr/local/bin/entrypoint.sh

ENV FLAG1 PXL{placeholder1}

EXPOSE 80

ENTRYPOINT ["/usr/local/bin/entrypoint.sh"]
CMD ["nginx", "-g", "daemon off;"]
```

Note that this uses a base Nginx image, sets a `FLAG1` environment variable, and runs an entrypoint script.

The environment variables in the Dockerfile (`FLAG1` and `FLAG2`) are placeholders. The SecLabs platform will override these with unique values for each team when containers are started.

Let's create this `entrypoint.sh` file in our `seclabs` folder:

```bash
#!/bin/bash
sed -i "s/{FLAG1}/${FLAG1}/g" /usr/share/nginx/html/robots.txt
sed -i "s/{FLAG2}/${FLAG2}/g" /usr/share/nginx/html/administrator.html
exec "$@"
```

Tip: Make sure your IDE uses LF rather than CRLF (Windows), or your container may crash.

Let's now build the container using Docker:

```bash
docker build -t username/helloseclabs .
```

You can test the container with the following command. It should display the `PXL{placeholder}` value when you visit `http://localhost` on your machine:

```bash
docker run -p 80:80 username/helloseclabs
```

## Creating the challenge

Navigate to our back office, create a new challenge, and use the following values:

- Challenge name: yourName-first-container-challenge
- GitHub repository: your unique repository identifier following the structure `<username>/<repo>` from our previous tutorial. For me, this was `d-ries/hello-seclabs`.
- README path: You can leave this set to `README.md` unless the path to your Markdown file is different.
- Challenge type: container
- Container image: your unique repository identifier following the Docker Hub structure `username/repo`. For me, this was `driessw/helloseclabs`.
- Container ports: 80
- Protocol: HTTP
- Difficulty level: beginner
- Points per flag: 10
- Description: tutorial - My first container challenge

For the environment variables, click Add variable and use the following settings:

- Key: FLAG1
- Value: leave empty
- Check the box labelled `This is a flag`

When you create the challenge, the platform will automatically:

- Generate unique MD5 hash flags for all existing accounts linked to this challenge
- Store flag mappings in the database
- Inject these flags as environment variables when students start containers
- Each team will receive different flag values for `FLAG1` and `FLAG2`

Note that we used the entrypoint script to set the correct values using a `sed` command in a simple HTML page, but nothing stops you from running more advanced commands in the entrypoint script to get the flag value where it needs to be. Some examples may include:

- using hex editors to inject flags into Wireshark files
- running encryption commands to create an encrypted file containing the unique flag value
- passing unique values at runtime
- ...

To finish up, add the new challenge to your challenge pool and test it using the student account you created earlier. Start the container on the student platform. After visiting the container URL, you should see a unique flag that you can validate using the flag validator.

## AI assisted challenge creation

Want an AI agent to assist you? You can use [this file](https://backoffice.seclabs.be/claude.md) as context for AI agents to help you build challenges that use the flag injection system.