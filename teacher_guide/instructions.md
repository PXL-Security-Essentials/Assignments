# Creating Our First Challenge
Let's navigate to the Challenges section in our [back office](https://backoffice.seclabs.be) and click the Create challenge button.

You'll notice that we need quite a lot of information to create a challenge. The first thing we need is a GitHub repository with a Markdown file containing our assignment instructions:
- Go to GitHub and create a new repository (e.g., d-ries/hello-seclabs)
- Add a README.md file with challenge instructions for students
- Add the following content to your `README.md` file:
```markdown
# My first challenge
Please be kind! I am still learning

## Objective 1
Follow these instructions:
- step 1
- step 2
- step 3
```
- Make the repository public. We'll talk about private repositories later on.

Now that we have our GitHub repository, we can return to the Create challenge page and fill in the following values:
- Challenge name: yourName-first-challenge
- GitHub repository: your unique repository identifier following the structure `<username>/<repo>`. For me, this was `d-ries/hello-seclabs`.
- README path: You can leave this set to `README.md` unless the path to your Markdown file is different.
- Challenge type: instructions. We'll look into the other options later.
- Difficulty level: beginner
- Points per flag: 0
- Description: tutorial - My first challenge

Then click the `Create challenge` button.

You've successfully created your first challenge, but it is not yet accessible to students. Navigate to the `Challenge pool` section and click the `Create pool` button. For the name, use `tutorial <yourname>` and make sure you select the challenge you just created.

Your challenge pool will now be visible in the list on our Challenge pool page, but it has not yet been assigned to students. Under the `Actions` tab, click the Assign students icon and assign your personal student account to the pool. After refreshing the student portal, you should now be able to see the challenge pool and the challenge you just created!

Want to add some dynamic quizzes to your challenges? Use the syntax below in your Markdown file. These will render as multiple-choice or open-ended questions in SecLabs:
```
~QUIZ
Q: What is the chemical symbol for Gold?
A) Go
B) Gd
C) Au
D) Ag
ANSWER: C
~
```
```
~QUESTION
Q: What is the name of the current US president?
ANSWER: Donald Trump
~
```
Note that these questions and answers are not tracked by the SecLabs system, and the answers are visible in the source code of our app. If you want to provide questions for grading, we advise you to create a Blackboard test to use alongside our platform.

You'll notice that the instruction-type challenge is rather simple. We don't provide students with any files or containers running applications that they have to use. We'll change that in the next part of the tutorial.

# Creating a Challenge with a File Download
The `file download` challenge type isn't much different from the `instructions` type. The only change is that we get an extra `download URL` field, which has to contain a direct URL to a file that students have to download. If you want to try this type of challenge, edit the challenge you created earlier and change the type to `file-download`. For the download URL, you can use `https://backoffice.seclabs.be/claude.md`.

Now navigate to your `README.md` file on GitHub and add the following section to the bottom of your instructions:
```
Download the file linked at the top of this assignment and open it. Then answer the question below:

~QUIZ
Q: What is the content of this file?
A) A file introducing us to a person named Claude
B) A recipe for pancakes
C) A file that we can use as a skill for our AI agent to help us build seclab container challenges
D) There is no file
ANSWER: C
~
```

Note that these files can't contain dynamic flags when we do it this way. A more advanced option would be to create a container challenge that runs a web server to serve the file with a dynamic flag injected, but more on this topic later.