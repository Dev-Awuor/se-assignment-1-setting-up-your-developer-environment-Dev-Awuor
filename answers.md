 Developer Environment Setup Documentation

 Overview
This document outlines the steps taken to set up a developer environment, including configurations, customizations, and troubleshooting measures. It also reflects on challenges faced during the setup and strategies used to overcome them.

1. Operating System Installation
OS Chosen: Ubuntu 22.04 LTS

Steps:

1. Download ISO: Downloaded Ubuntu 22.04 LTS ISO from the official website.
2. Create Bootable USB**: Used Rufus to create a bootable USB drive.
3. Install OS: Booted from USB and followed on-screen instructions to install Ubuntu.

2. Basic System Configuration
Steps:
1. Update System:

   ```sh
   sudo apt update && sudo apt upgrade -y
   ```

2. Install Essential Tools:

   ```sh
   sudo apt install build-essential curl file git
   ```

3. Setting Up Version Control (Git)
Steps:
1. Install Git:

   ```sh
   sudo apt install git
   ```

2. Configure Git:

   ```sh
   git config --global user.name "Your Name"
   git config --global user.email "your.email@example.com"
   ```

4. Installing Programming Languages and Runtimes
 Python:
1. Install Python:

   ```sh
   sudo apt install python3 python3-pip
   ```

2. Configure Pip:

   ```sh
   pip3 install --user virtualenv
   ```

 Node.js:
1.Install Node.js and npm:

   ```sh
   curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
   sudo apt install -y nodejs
   ```

5. Setting Up Integrated Development Environment (IDE)
 Visual Studio Code

 Steps:

1. Download and Install VS Code:

   ```sh
   sudo snap install --classic code
   ```

2. Install Extensions:
   - Python
   - Prettier - Code formatter
   - ESLint
   - GitLens

6. Configuring Shell and Terminal
Chosen Shell**: Zsh with Oh My Zsh

 Steps:

1. install Zsh:

   ```sh
   sudo apt install zsh
   ```

2. Install Oh My Zsh:

   ```sh
   sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
   ```

3. Set Zsh as Default Shell:

   ```sh
   chsh -s $(which zsh)
   ```

7. Docker Installation
Steps:
1.Install Docker:

   ```sh
   sudo apt install apt-transport-https ca-certificates curl software-properties-common
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
   sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
   sudo apt update
   sudo apt install docker-ce
   ```

2. Post-installation Steps:

   ```sh
   sudo groupadd docker
   sudo usermod -aG docker $USER
   newgrp docker
   ```

8. Configuring VS Code for Docker
1. Install Docker Extension**:
   - Docker Extension by Microsoft

 Challenges and Solutions

1. Issue: Slow internet during package downloads.
   - Solution Switched to a more reliable network and used a wired connection instead of Wi-Fi.
2.Issue**: Permission errors with Docker.
   - Solution: Ensured correct group memberships and restarted the system after changes.

Reflection
Setting up the developer environment was a straightforward but meticulous process. Ensuring all dependencies and configurations were correctly set up took time, and troubleshooting permission issues with Docker was particularly challenging. Overcoming these by checking user group memberships and proper documentation helped streamline the process. Future setups will benefit from this documented procedure, ensuring a smoother and quicker setup.
