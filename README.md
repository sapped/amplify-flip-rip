# amplify-flip-rip
Serverless, full-stack personal site using AWS Amplify. This deprecates former personal site repo. Keeping that up to retain bespoke devops work (nginx, etc.)

# Prerequisites
Not going to get too detailed here, these are just the steps you need to do first. Of course, you can skip any that you've already done.
1. Install nvm [(node version manager)](https://github.com/nvm-sh/nvm)
    - $ cd ~
    - $ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
    - restart terminal (exit, reopen)
    - `nvm -v`
    - "0.39.1"
2. Install node.js
    - `nvm install node`
    - "now using node v18.7.0"
3. Install AWS CLI
    - [details in this tutorial](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
    - `sudo apt-get update`
    - `sudo apt-get upgrade`
    - `sudo apt install unzip`
    - `cd ~`
    - `curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"`
    - `unzip awscliv2.zip`
    - `sudo ./aws/install`
    - `/usr/local/bin/aws --version`
    - "aws-cli/2.7.21 Python/3.9.11 Linux/5.10.16.3-microsoft-standard-WSL2 exe/x86_64.ubuntu.20 prompt/off"
    - `rm -rf awscliv2.zip`
4. Install Amplify CLI
    - Per easy AWS tutorial linked below
    - `npm install -g @aws-amplify/cli`
5. Install Amazon Corretto
    - [Amazon Corretto (Java package) install steps here, for amplify mock api command](https://docs.aws.amazon.com/corretto/latest/corretto-11-ug/generic-linux-install.html)
    - `wget -O- https://apt.corretto.aws/corretto.key | sudo apt-key add - 
 sudo add-apt-repository 'deb https://apt.corretto.aws stable main'`
    - ` sudo apt-get update; sudo apt-get install -y java-11-amazon-corretto-jdk`
6. Sign up for AWS Account

# AWS Basic Tutorial
Let's follow an [easy AWS tutorial](https://docs.amplify.aws/start/getting-started/data-model/q/integration/react/) to setup the basics of our app. This will continue to serve as a useful reference. Recommend revisiting daily for the first few weeks. This tutorial will give us: React Frontend, GraphQL API, Authentication. Everything powered by Amplify.