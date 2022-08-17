# amplify-flip-rip
Serverless, full-stack personal site using AWS Amplify. This deprecates former personal site repo. Keeping that up to retain bespoke devops work (nginx, etc.). Most of this was coded on Ubuntu on WSL2, though some was also done on a macbook. Code may change (such as nvm install) if you're running on a Macbook, since the below is mostly assuming you're on Ubuntu 20.04.

[See staging live!](https://master.d2nqnxtyleq1gm.amplifyapp.com/)

# Prerequisites
Not going to get too detailed here, these are just the steps you need to do first. Of course, you can skip any that you've already done.
1. Install nvm [(node version manager)](https://github.com/nvm-sh/nvm)
    - [Mac instructions here](https://tecadmin.net/install-nvm-macos-with-homebrew/), otherwise Ubuntu instructions
    - `$ cd ~`
    - `$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash`
    - restart terminal (exit, reopen)
    - `nvm -v`
    - "0.39.1"
2. Install node.js
    - `nvm install node`
    - `node -v`
    - "now using node v18.7.0"
3. Install AWS CLI
    - [Details in this tutorial (commands below pasted for Linux, though MacOS also listed)](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
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
    - `npm install -g @aws-amplify/cli`
    - ^ command found in the "easy tutorial" that we work through below, more details there if you want to dig in (not sure why you would lol)
5. Install Amazon Corretto
    - [Amazon Corretto (Java package) install steps here, for amplify mock api command](https://docs.aws.amazon.com/corretto/latest/corretto-11-ug/generic-linux-install.html)
    - `wget -O- https://apt.corretto.aws/corretto.key | sudo apt-key add - 
 sudo add-apt-repository 'deb https://apt.corretto.aws stable main'`
    - ` sudo apt-get update; sudo apt-get install -y java-11-amazon-corretto-jdk`
6. Sign up for AWS Account
7. Follow the AWS Basic Tutorial, per below.

# AWS Basic Tutorial
Pre-tutorial notes:
    - CI/CD is pretty nifty & easy to setup. I went that route, personally. You don't have to, the tutorial uses "Manual." But it's not hard to do the CI/CD, which is nifty.
    - When you get to the bit where you do "amplify add hosting" and the browser opens, you'll see a bit that says "edit build settings." This is a good time to specify your desired python version. The default is 3.7, you may want to upgrade it to 3.8 or 3.9. [Instructions here](https://github.com/aws-amplify/amplify-hosting/blob/main/FAQ.md#how-do-i-run-amplify-functions-with-python-runtime) per comment on Jan 21, 2021 in [this original GitHub issue thread](https://github.com/aws-amplify/amplify-hosting/issues/595). If it doesn't let you edit build settings upon creation, you can do it right after, it's OK. I'm currently getting a bug that doesn't let me edit it at build, so no worries if you have the same issue.

Let's follow an [easy AWS tutorial](https://docs.amplify.aws/start/getting-started/data-model/q/integration/react/) to setup the basics of our app. This will continue to serve as a useful reference. Recommend revisiting daily for the first few weeks. This tutorial will give us: React Frontend, GraphQL API, Authentication. Everything powered by Amplify.

## Bugs I Encountered
- https://itsmycode.com/error-digital-envelope-routines-unsupported/

# Invoicing App
Simple app to generate and track invoices

## Data Model

Cover Message
- Body
- Job name

Freelancer Details
- Image Logo
- Freelancer Name
- Freelancer Address
- Freelancer Phone

Customer Details
- Customer ID
- Customer Name
- Customer Address
- Customer Phone
- Customer Email
- Customer Site

Invoice Details
- Invoice ID
- Issuance date of invoice
- Due date of invoice
- Short Description, Terms of invoice (due on receipt, 30 days, etc.)
- Check payable to
- Zelle details
- Direct deposit details

Footer
- COI notice ($7.5k min, etc.)
- Description of late fees

Description of Charges
- List of Charges
    - Date
    - Description
    - Quanitity
    - Base Rate
    - Multiplier
    - Amount
- Total
- Payment Received
- Balance Due

## Features
- Deposit big job auto-calculator (30% or 50% etc.)
- Hourly for 8 hour OT
- Hourly for 10 horu OT