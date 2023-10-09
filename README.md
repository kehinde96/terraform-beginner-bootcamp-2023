# Terraform Beginner Bootcamp 2023

## Semantic Versioning
This project is going to utilize semantic versioning for its tagging
[semver.org](https://semver.org/)



The general format:

**MAJOR.MINOR.PATCH**, eg. `1.0.1`

 - **MAJOR** version when you make incompatible API changes
 - **MINOR** version when you add functionality in a backward compatible manner
 - **PATCH** version when you make backward compatible bug fixes

 ## Install the Terraform CLI
 The Terraform installation instructions have changed due to gpg keyring changes. So we need to refer to the latest install CLI instructions via Terraform  Documentation and change the scripting for installation.

 [Install Terraform CLI](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli)

 ### Refactoring into Bash Scripts
 While fixing the Terraform CLI gpg depreciation issues we noticed that bash script steps were a considerable amount of code. so we decided to create a bash script to install the Terraform CLI

This bash script is located here:[./bin/install_terraform_cli](./bin/install_terraform_cli)

- This will keep the Gitpod Task file tidy.([.gitpod.yml](.gitpod.yml))
- This will allow better portability for other
- This allows us an easier to debug and execute manually Terraform CLI install

#### Shebang Considerations

A shebang(pronounced Sha-bang) tells the bash script what program will intercept the script. eg. `#!/bin/bash`

ChatGPT recommended this format for bash : `#!/usr/bin/env.bash`

- for portability for different OS distributions
- Will search the user's PATH for the bash executable

When executing the bash script we can use the `./` shorthand notation to execute the bash script.

https://en.wikipedia.org/wiki/Shebang_(Unix)

#### Execution Considerations 

When executing the bash script we can use the `./` shorthand notation to execute the bash script. 
eg.`./bin/install_terraform_cli`
if we are using a script in .gitpod.yml we need to point the script to a program to interpret it.
eg. `source ./bin/install_terraform_cli`

#### Linux Permissions Consideration

In order to make our bash script executable we need to change linux permission for the fix to be executable at the user mode.
```sh
chmod u+x ./bin/install_terraform_cli
```

alternatively:

```sh
chmod 744 ./bin/install_terraform_cli
```

https://en.wikipedia.org/wiki/Chmod

### Gitpod Lifecycle (Before, Init, Command)

We need to be careful when using the Init because it will not rerun if we restart an existing workspace.

 https://www.gitpod.io/docs/configure/workspaces/workspace-lifecycle



### Consideration for Linux Distribution 

This project is built against Ubuntu.
Please consider checking your Linux Distribution and change according to distribution needs.

[How to check OS Version in Linux](https://www.cyberciti.biz/faq/how-to-check-os-version-in-linux-command-line/)

Example of checking OS Version:
```
$ cat /etc/os-release
PRETTY_NAME="Ubuntu 22.04.3 LTS"
NAME="Ubuntu"
VERSION_ID="22.04"
VERSION="22.04.3 LTS (Jammy Jellyfish)"
VERSION_CODENAME=jammy
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=jammy
```

 
 
 
 
