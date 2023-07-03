# Warden discord.py bot

Warden is a multi-purpose Discord bot that is currently under development. It aims to provide various functionalities and features by utilizing different APIs. 
Please note that Warden is primarily intended for testing purposes and may not have a stable release yet.


## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Tutorial](#tutorial)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Introduction

Warden is a Discord bot designed to assist server administrators and provide a range of features. It is being developed to interact with various APIs, allowing it to perform diverse tasks within Discord servers. Please be aware that Warden is still in the development phase, and features may be subject to change.

## Features

List the key features and functionalities of your project. Include a brief description for each feature.

- Feature 1: Description
- Feature 2: Description
- Feature 3: Description

## Tutorial
<details>

<summary> Step by step coding tutorial for ubuntu linux </summary>

1. Create a python venv (Virtual Environment)
- Create directory in your home directory to store all venvs: 
`mkdir ~/.venvs`
- Create venv using python: 
`python3 -m venv ~/.venvs/discord`
- Before installing requirements, activate the venv 
`source ~/.venvs/discord/bin/activate`
- Your prompt should look like this now: "(discord) user@host:~$"
- You can now install requirements using:
`pip install discord.py`
`pip install python-dotenv`
- Create directory to contain project's files & go into created directory:
`mkdir warden-bot`
- Save your environment's requirements to a file:
`pip freeze > requirements.txt`
2. Build the simple bot
- Go to your venv directory then create and open .env file
`touch .env`
`vi .env`
add the following lines 
    - Replace Y0UR.DISCORD-.TOKEN-FROM-DISCORD with your discord token
    - Replace YOURGUILDID with your server's (guild) id
```
DISCORD_TOKEN=Y0UR.DISCORD-.TOKEN-FROM-DISCORD
GUILD_ID=YOURGUILDID
```
- Create file to start coding and open it using editor of your choice:
`touch warden.py`
`vi warden.py`
- Add the following imports 
```
import discord # import discord.py library
import os # to get token from .env file
from dotenv import load_dotenv
```
- Retrieve the Discord API token and your guild from environment variables
```
load_dotenv()
DISCORD_TOKEN = os.getenv('DISCORD_TOKEN') 
GUILD_ID = os.getenv('GUILD_ID') #discord.Object(id=gggguuuuiiillldddID)
```
- Add the discord's intents
```
intents = discord.Intents.default()
client = discord.Client(intents=intents)
```
- Example code
```
import discord
import os
from dotenv import load_dotenv

load_dotenv() #load dotenv variables
discord_token = os.getenv('DISCORD_TOKEN')
discord_guild = os.getenv('DISCORD_GUILD')

class MyClient(discord.Client):
    def __init__(self, intents):
        super().__init__(intents=intents)
    async def on_ready(self):
        print(f"Logged in as { self.user.name } (ID:{ self.user.id })")
        print(f"discord.py API version: { discord.__version__ }")
        print(f"------------------------------------------------")
        print(f"Setting {self.user.name}'s status to { 'do not disturb','r' }")

        await self.change_presence(status=discord.Status.dnd)

intents = discord.Intents.default()
intents.message_content = True
intents.voice_states = True

client = MyClient(intents=intents)
client.run(discord_token)
```

> Still much to do... :)
</details>

## Installation

Step-by-step instructions on how to install and set up your project. Include any dependencies or prerequisites that need to be installed beforehand.

1. Step 1: Clone the repository
2. Step 2: Install the dependencies: `pip install -r requirements.txt`
3. Step 3: Set up the required API credentials. Refer to the documentation for each API used.
4. Step 4: Configure the bot token and other settings in the .env file.
5. Step 5: Start the bot: `python warden.py`

## Usage

//TODO!// How to use project. Examples and code snippets where applicable. Any configuration options or command-line parameters that can be used. -- 

1. Step 1: Description
2. Step 2: Description
3. Step 3: Description

## Contributing

Provided guidelines for submitting bug reports, feature requests, or pull requests.

Contributions to Warden are welcome! If you'd like to contribute, please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Commit your changes and push them to your forked repository.
4. Open a pull request, providing a detailed explanation of your changes.

Please adhere to the code style guidelines and ensure your code passes all tests before submitting a pull request.

## License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).

---