# Local LLM Setup Guide

This repository contains all the necessary scripts, configuration files, and documentation required to set up and run two different large language models (LLMs) locally: Llama3 using the Ollama Python library, and [Second Model Name]. This project was created as part of Prompt Engineering Class to demonstrate practical skills in handling sophisticated machine learning models directly on a local machine.

## Overview

The goal of this project is to:
- Download, install, and run the Llama3 model using the Ollama library.
- Download, install, and run a second LLM of choice.
- Document the setup process and interactions with both models using the curl command.
- Compare the performance of both models using identical prompts.

## Repository Contents

- `llama3/`: This directory contains all scripts and files needed to set up and run the Llama3 model.
- `[Second Model Name]/`: This directory includes all necessary scripts and files for the second chosen model.
- `README.md`: This file, which provides an overview and setup instructions.
- `setup_scripts/`: Contains any scripts used to automate parts of the installation process for both models.
- `configurations/`: Configuration files necessary for running the models.

## Setup Instructions

### Llama3 Installation and Usage Guide

This guide provides step-by-step instructions for installing and running the Llama3 model locally using the Ollama Python library. Each step is explained in detail to ensure a smooth setup and operation.

#### Prerequisites

Before proceeding, ensure that you have the following prerequisites installed on your system:
- **Python 3.x**: The programming language used to interact with Llama3. Ensure Python 3.x is installed as the Ollama library is compatible with Python 3.
- **pip**: The Python package installer, used to install the Ollama library. Comes installed with Python 3.4 and above.

#### Installation Steps

#### Step 1: Install Ollama Service

The Ollama service acts as a server on your local machine that facilitates communication between the Python script and the Llama3 model.

1. **Download and Install the Ollama Service**:
   - Open a terminal window. This is where you will enter commands to install software.
   - Run the following command. This command downloads and executes a shell script that installs the Ollama service:
     ```bash
     curl https://ollama.ai/install.sh | sh
     ```

2. **Start the Ollama Service**:
   - After installation, start the service by executing:
     ```bash
     ollama serve
     ```
   - This command launches the Ollama server, which will listen for requests from the Python library.

#### Step 2: Install Ollama Python Library

This library provides a Python interface to interact with the Llama3 model through the Ollama service.

1. **Install the Library**:
   - Use pip to install the Ollama Python library by running:
     ```bash
     pip install ollama
     ```

### Using Llama3 with Ollama Python Library

#### Basic Interaction

Interact with Llama3 by sending text prompts and receiving text responses.

1. **Create a Python Script**:
   - Use a text editor or an Integrated Development Environment (IDE) to create a Python script named `llama_interaction.py`.

2. **Write the Interaction Code**:
   - Incorporate the following Python code in your script. This code initializes the Ollama library, sends a prompt to Llama3, and prints the response.
     ```python
     import ollama

     response = ollama.chat(model='llama3', messages=[{'role': 'user', 'content': 'Why is the sky blue?'}])
     print(response['message']['content'])
     ```

3. **Run Your Script**:
   - Execute the script from the terminal to see Llama3’s response:
     ```bash
     python llama_interaction.py
     ```

#### Streaming Responses

For applications requiring real-time interaction, you can stream responses from Llama3.

1. **Modify Your Python Script for Streaming**:
   - Edit `llama_interaction.py` to enable streaming. This modification changes how responses are received, making them real-time as the model generates them:
     ```python
     import ollama

     stream = ollama.chat(
         model='llama3',
         messages=[{'role': 'user', 'content': 'Why is the sky blue?'}],
         stream=True
     )

     for chunk in stream:
       print(chunk['message']['content'], end='', flush=True)
     ```

2. **Run the Streaming Script**:
   - Run the modified script to start receiving streamed responses:
     ```bash
     python llama_interaction.py
     ```

### Troubleshooting

If issues arise:
- **Check Service**: Ensure the Ollama service is actively running in the background.
- **Script Errors**: Verify there are no syntax or runtime errors in your Python script.
- **Dependencies**: Confirm all required dependencies are correctly installed and are compatible versions.

By following these detailed instructions, you should be able to successfully set up and interact with the Llama3 model locally. For further guidance or advanced configurations, refer to the official [Ollama documentation](https://ollama.ai/docs).


### GPT4All Installation and Usage Guide

This guide provides comprehensive instructions for installing and running the GPT4All model locally on your CPU. Each step is detailed to help you understand and execute the setup successfully.

#### Prerequisites

Before you start, make sure you have the following:
- **Git**: Required to clone the repository. Install Git from [here](https://git-scm.com/downloads).
- **Adequate disk space**: Ensure you have enough space to download the model and its dependencies.

#### Installation Steps

#### Step 1: Clone the Repository

Start by cloning the GPT4All repository to your local machine. It is recommended to clone it into a new directory named "GPT4All".

1. **Open your terminal or command prompt**:
   - Access your terminal on Linux or macOS, or Command Prompt/PowerShell on Windows.

2. **Clone the repository**:
   - Run the following command to clone the repository:
     ```bash
     git clone https://github.com/nomic-ai/gpt4all.git
     ```
   - This command creates a local copy of the GPT4All repository in a directory named `GPT4All` on your machine.

#### Step 2: Download the Model Checkpoint

The next step is to download the GPT4All CPU quantized model checkpoint.

1. **Download the model checkpoint**:
   - Use the following direct download link to get the model file:
     ```plaintext
     https://the-eye.eu/public/AI/models/nomic-ai/gpt4all/gpt4all-lora-quantized.bin
     ```
   - Alternatively, if available, use a torrent magnet link to download the file using a BitTorrent client.

2. **Move the downloaded file**:
   - Once the download is complete, move the `gpt4all-lora-quantized.bin` file to the `chat` folder within the cloned repository directory.

#### Step 3: Navigate to the Chat Folder

Navigate to the chat folder where you moved the model checkpoint.

1. **Change directory**:
   - In your terminal or command prompt, run:
     ```bash
     cd gpt4all/chat
     ```
   - This command changes the current directory to the `chat` folder inside the cloned repository.

#### Step 4: Run the Model

Run the model using the command specific to your operating system.

1. **Execute the model**:
   - Depending on your operating system, use one of the following commands:
     - **Windows (PowerShell)**:
       ```bash
       ./gpt4all-lora-quantized-win64.exe
       ```
     - **M1 Mac/OSX**:
       ```bash
       ./gpt4all-lora-quantized-OSX-m1
       ```
     - **Linux**:
       ```bash
       ./gpt4all-lora-quantized-linux-x86
       ```
     - **Intel Mac/OSX**:
       ```bash
       ./gpt4all-lora-quantized-OSX-intel
       ```
   - These commands start the GPT4All model on your machine, allowing you to interact with it through your terminal or command prompt.

#### Usage

Once the model is running, interact with it by entering text queries. It will respond similarly to ChatGPT, though response times may vary based on your CPU performance.

#### Updating the Installation

To keep your GPT4All installation up to date, periodically pull the latest changes from the repository:
- Navigate to your main install folder and run:
  ```bash
  git pull


