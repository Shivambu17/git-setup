# GitHub SSH Setup Guide

This guide provides step-by-step instructions to set up SSH keys for GitHub on both Windows and Linux. SSH keys provide a secure way of connecting to GitHub without needing to enter your username and password every time you interact with your repositories.

## Table of Contents

1. [Prerequisites](#prerequisites)
2. [Setup on Windows](#setup-on-windows)
   - [Generate SSH Key](#generate-ssh-key-on-windows)
   - [Add SSH Key to SSH Agent](#add-ssh-key-to-ssh-agent-on-windows)
   - [Add SSH Key to GitHub](#add-ssh-key-to-github)
   - [Verify the SSH Connection](#verify-the-ssh-connection)
3. [Setup on Linux](#setup-on-linux)
   - [Generate SSH Key](#generate-ssh-key-on-linux)
   - [Add SSH Key to SSH Agent](#add-ssh-key-to-ssh-agent-on-linux)
   - [Add SSH Key to GitHub](#add-ssh-key-to-github)
   - [Verify the SSH Connection](#verify-the-ssh-connection)

## Prerequisites

- A GitHub account. If you don't have one, you can sign up [here](https://github.com/join).
- Git installed on your machine. You can download and install Git from [here](https://git-scm.com/downloads).

## Setup on Windows

### Generate SSH Key on Windows

1. Open PowerShell or Git Bash.
2. Run the following command to generate a new SSH key. Replace `your_email@example.com` with your GitHub email address:
```sh
   ssh-keygen -t rsa -C "your_email@example.com"
```
If your system does not support Ed25519, use:

```sh

ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
 
3. Press Enter to accept the default file location.
4. When prompted, enter a passphrase (optional but recommended).

6. Add SSH Key to SSH Agent on Windows

    Start the SSH agent in the background:

```sh

eval $(ssh-agent -s)
```

7. Add your SSH private key to the SSH agent. Replace rsa if you used a different filename:

``` sh

    ssh-add ~/.ssh/rsa
```
8. Add SSH Key to GitHub

    Copy the SSH public key to your clipboard:

```sh

    cat ~/.ssh/rsa.pub
```
- Go to GitHub SSH settings.
- Click New SSH key.
- In the "Title" field, add a descriptive label for the new key (e.g., "My Windows PC").
- Paste your SSH key into the "Key" field.
 - Click Add SSH key.

9. Verify the SSH Connection

  - Open PowerShell or Git Bash and run:

```sh

ssh -T git@github.com
```
 - You should see a message like:


- Hi your-username! You've successfully authenticated, but GitHub does not provide shell




This README provides clear, step-by-step instructions for setting up SSH keys on both Windows and Linux systems and includes verification steps to ensure the keys are working correctly.
