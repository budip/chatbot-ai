# ChatterBot: Build a Chatbot with Python

Welcome to the unofficial repository for building a Python chatbot with ChatterBot! This project accompanies the [building a Python chatbot with ChatterBot](https://realpython.com/build-a-chatbot-python-chatterbot/), offering a practical guide to creating an intelligent chatbot with ease. Originally developed in a Virtual Environment (venv), this version is now fully containerized with **Docker**, streamlining the setup and deployment process for a seamless experience.


### Requirements
Requirements to Run the Project:
1. Docker Desktop
    - Platform: Available for macOS, Windows, and Linux.
    - Version: Ensure it’s up-to-date to support Docker Compose v2.
2. Project Files
    - Includes Dockerfile, docker-compose.yml, and Python scripts.
3. Basic Docker Knowledge
    - Familiarity with commands like docker compose up and docker compose build is helpful.

### Project Structure
<small><small>
```bash
chatbot/
├── app/
│   ├── bot.py
│   ├── chat.txt
│   ├── cleaner.py
│   └── db.sqlite3
├── docker-compose.yml
├── Dockerfile
├── README.md
└── requirements.txt
```
 </small></small>


### Build Instructions

1. **Ensure All Related Containers Are Down**
   
   Before building, make sure all containers related to this project are stopped and removed:
   <small>
   ```bash
   docker-compose down --remove-orphans
   ```
    </small>

2. **Build the Docker Container**
    Use the following command to build the Docker container:
    <small>
    ```bash
    docker compose build
    ```
    </small>
    
    <small><small>
    ```bash
    [+] Building 0.1s (11/11)FINISHED
    docker:desktop-linux
    => [python_app internal] load build definition from Dockerfile
    => => transferring dockerfile: 436B
    => [python_app internal] load metadata for docker.io/library/python:3.9-slim
    => [python_app internal] load .dockerignore
    => => transferring context: 2B
    => [python_app 1/5] FROM docker.io/library/python:3.9-slim
    => [python_app internal] load build context
    => => transferring context: 636.77kB
    => CACHED [python_app 2/5] WORKDIR /app
    => CACHED [python_app 3/5] COPY requirements.txt .
    => CACHED [python_app 4/5] RUN pip install --no-cache-dir -r requirements.txt
    => [python_app 5/5] COPY . .
    => [python_app] exporting to image
    => => exporting layers
    => => writing image sha256:43fc701e7edaec220bfcfa0e0b3db7e3a7a2910a263fd72e3cf35df8fc2c3a15
    => => naming to docker.io/library/chatbot-python_app
    => [python_app] resolving provenance for metadata file
    ```
    </small></small>

3. **Run the Container and Attach**
    Start the container in detached mode:
    <small>
    ```bash
    docker compose up -d
    ```
    </small>

    <small><small>
    ```bash
    [+] Running 1/1
    ✔ Container chatbot  Started                                                                                
    ```
    </small></small>                                                                

4. **Execute the App in Bash Mode**
    Enter the container’s shell to interact with the app:
    <small>
    ```bash
    docker compose run --rm python_app /bin/bash
    ```
    </small>
    You should see the terminal prompt change to <u>root@74dff0144163:/app#</u>, indicating you’re now inside the container.

    <small><small>
    ```bash
    chatbot % docker compose run --rm python_app /bin/bash
    root@74dff0144163:/app# 
    ```
    </small></small>                                                                


5. **Run the Bot and Start Chatting**
    <small>
    ```bash
    python3 bot.py
    ```
    </small>

    <small><small>
    ```
    root@74dff0144163:/app# python3 bot.py
    [nltk_data] Downloading package averaged_perceptron_tagger to
    [nltk_data]     /root/nltk_data...
    [nltk_data]   Unzipping taggers/averaged_perceptron_tagger.zip.
    [nltk_data] Downloading package punkt to /root/nltk_data...
    [nltk_data]   Unzipping tokenizers/punkt.zip.
    [nltk_data] Downloading package stopwords to /root/nltk_data...
    [nltk_data]   Unzipping corpora/stopwords.zip.
    [nltk_data] Downloading package wordnet to /root/nltk_data...
    List Trainer: [####################] 100%
    > 
    ```
    </small></small>                                                                


### Interact with the Bot
<small><small>
```
> hi
🪴 Welcome, friend 🤗
> thanks for the green welcome
🪴 I let you
> you let me be here?
🪴 It's a monsters!
> did you mean monstera?
🪴 The leafs that she had are getting dryer and dryer. But she’s also growing plenty of new ones
> who?
🪴 Do raindrops touch their leaves?
> very philosophical!
🪴 Lol
> ;)
🪴 I don't grow any crop at home
> no crops in pots
🪴 Ah, gotcha!
```
</small></small> 


### Explore the Project

You’ll find the code for each step of the tutorial in a separate folder. The folders also include a SQLite database that contains the different phases of training at each step. Because of this, you can inspect the project at different stages and notice how it evolves when you add more data and interactions.

### Key Points
- **Clear Sectioning**: The new sections, "Interact with the Bot" and "Explore the Project," are clearly delineated with headers that reflect their content.
- **Realistic Example Interaction**: The interactive chat example is formatted in a way that mirrors a real terminal session.
- **Consistent Formatting**: The formatting remains consistent throughout the document, maintaining clarity and readability.

This organization makes it easy for users to follow along with the steps, interact with the chatbot, and explore the project in detail.