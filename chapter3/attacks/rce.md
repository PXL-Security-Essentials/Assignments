# Basic remote code execution

## Background

Victor Ashwood, the eccentric owner of Darkwood Manor, has been found dead in his living room. The manor's power has been cut, and the only thing still running is a basement terminal — an automation system Victor built himself using bash scripts.

You have been given remote access to the terminal. Your job: investigate the scene, find the truth, and seal the evidence.

## Access

Navigate to the challenge IP in your browser. You will be greeted by an interactive text adventure — the manor's automation terminal.

## Gameplay

The terminal accepts natural language commands. Some useful ones to get started:

| Command | Description |
|---|---|
| `look` | Examine your current surroundings |
| `go <room>` | Move to another room |
| `check <item>` | Inspect an item up close |
| `read <item>` | Read a document or note |
| `search <query>` | Search the evidence logs |
| `help` | List all commands |

Available rooms: `living_room`, `kitchen`, `library`, `basement`

## Tasks

1. Explore the manor. Read the notes, journal entries, and evidence logs scattered throughout the house. Pay attention to what they say about the terminal.

2. Understand the vulnerability. The `search` command passes your input to the system shell. What does that mean for what you can run?

3. Enumerate the system. Use the vulnerability to list files on the server. Find the `/game` directory.

4. Run the bash script `toggleLights.sh` through the terminal. Watch what happens to the page.

5. Validate the flag you find below.
