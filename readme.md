# Local LLM Setup Guide

This repository contains all the necessary scripts, configuration files, and documentation required to set up and run two different large language models (LLMs) locally: Llama3 using the Ollama Python library, and GPT4All. This project was created as part of Prompt Engineering Class to demonstrate practical skills in handling sophisticated machine learning models directly on a local machine.

## Overview

The goal of this project is to:
- Download, install, and run the Llama3 model using the Ollama library.
- Download, install, and run a second LLM of choice.
- Document the setup process and interactions with both models using the curl command.
- Compare the performance of both models using identical prompts.

## Repository Contents
- `GPT4ALL/`: This directory includes all necessary scripts and files for the second chosen model.
- `README.md`: This file, which provides an overview and setup instructions.
- 
## Setup Instructions

### Llama3 Installation and Usage Guide

### Ollama Installation Guide for Windows

This guide provides detailed instructions for downloading, installing, and configuring Ollama on your Windows machine to run large language models locally.

#### Prerequisites

Before you begin, ensure you have the following:
- **Windows 10 or higher**
- **Python 3.7 or higher**
- **Administrative privileges**

#### Step-by-Step Installation

#### 1. Download Ollama

1. Visit the [Ollama website](https://www.ollama.ai) and navigate to the downloads section.
2. Download the Windows installation package (e.g., `Ollama-Installer.exe`).

#### 2. Install Python

If you don't already have Python installed, download it from the [official Python website](https://www.python.org/downloads/) and follow the installation instructions.

#### 3. Install Ollama

1. Locate the downloaded `Ollama-Installer.exe` file.
2. Double-click the file to start the installation process.
3. Follow the on-screen instructions to complete the installation.

#### 4. Configure Environment Variables

1. Open the Start Menu and search for "Environment Variables".
2. Click on "Edit the system environment variables".
3. In the System Properties window, click on "Environment Variables".
4. Under System Variables, find and select the `Path` variable, then click "Edit".
5. Add the path to your Ollama installation directory (e.g., `C:\Program Files\Ollama`).
6. Click "OK" to save the changes.

#### 5. Install Required Python Packages

Open Command Prompt and run the following commands to install necessary Python libraries:
```sh
pip install numpy
pip install pandas
pip install tensorflow
```



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


