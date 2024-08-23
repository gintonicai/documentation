---
description: >-
  This page provide requirements for the user named Provider who provided
  computational resources to the machine.
---

# Setting Up Your Environment

## Prerequisites

Before joining the Compute Mining Subchain, ensure your machine meets the special  requirements:

* Operating System: Linux Ubuntu 20.04 or later
* python3.9 or higher
* GPU with minimum 2G VRAM&#x20;
* Video card drivers installed and the nvidia-smi package installed
* Account HuggingFace and an Access Token
* A valid blockchain wallet address

## Installation Steps

### Before starting

1. Provider opens the terminal and calls '/distillery-download' backend endpoint, then the Nginx server returns all necessary data to proceed, including initial\_peer address.
2. Script checks whether the Gintonic server is already installed.\
   a. If yes, it goes to step 3.\
   b. If not, Petals server installation starts. During installation system requirements and necessary drivers are checked.
3. In order to use the Distillery program you will need to:\
   **-** Create an account on [HuggingFace](https://huggingface.co/). \
   **-** Create an Access Token. Go to settings in your account, then Access Token -> New Token.\
   **-** Go to this [link ](https://huggingface.co/mistralai/Mixtral-8x7B-Instruct-v0.1)and confirm access to the repository.&#x20;

### Start Distillery

In order to use the script:

* Read the system requirements&#x20;
* Run the following command:\
  \
  `curl https://gintonic.sfxdx.com/distillery-download --output distillery`\
  _If the system writes 'curl command not found' , run the command 'sudo apt install -y curl'_
* Run the command 'chmod +x distillery'.
* Run the program with the command sudo './distillery'. You may need to enter a root password.
* Follow the instructions of the program.



\
