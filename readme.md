# Llama3 Installation and Usage Guide

This guide provides step-by-step instructions for installing and running the Llama3 model locally using the Ollama Python library. Each step is explained in detail to ensure a smooth setup and operation.

## Prerequisites

Before proceeding, ensure that you have the following prerequisites installed on your system:
- **Python 3.x**: The programming language used to interact with Llama3. Ensure Python 3.x is installed as the Ollama library is compatible with Python 3.
- **pip**: The Python package installer, used to install the Ollama library. Comes installed with Python 3.4 and above.

## Installation Steps

### Step 1: Install Ollama Service

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

### Step 2: Install Ollama Python Library

This library provides a Python interface to interact with the Llama3 model through the Ollama service.

1. **Install the Library**:
   - Use pip to install the Ollama Python library by running:
     ```bash
     pip install ollama
     ```

## Using Llama3 with Ollama Python Library

### Basic Interaction

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

### Streaming Responses

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

## Troubleshooting

If issues arise:
- **Check Service**: Ensure the Ollama service is actively running in the background.
- **Script Errors**: Verify there are no syntax or runtime errors in your Python script.
- **Dependencies**: Confirm all required dependencies are correctly installed and are compatible versions.

By following these detailed instructions, you should be able to successfully set up and interact with the Llama3 model locally. For further guidance or advanced configurations, refer to the official [Ollama documentation](https://ollama.ai/docs).

