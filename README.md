# Aws Developer getting started
Followed with windows

##Installing the CLI

1. Download the Aws Command Line Interface (https://aws.amazon.com/cli)
2. Execute `aws --version` and should see the aws version.

##Configure the AWS CLI
1. Configure AWS Access Key (enables CLI and SDK to access the account)
2. Security Credentials under `Your name` top menu
3. Open `Access Key` menu options
4. Create new access key (the key can only be downloaded once so save it)
5. On command line `aws configure` and follow the instructions
6. `aws ec2 describe-instances` to test, you should get and empty list