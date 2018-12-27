## Introduction

You can assume aws roles from the command line. This script like many others is just a small shortcut to make things easier and faster.

## Installation
sudo curl -L "https://raw.githubusercontent.com/virgiliolino/aws-assume/master/aws-assume" -o /usr/local/bin/aws-assume

sudo chmod +x /usr/local/bin/aws-assume

I'm assuming that you installed aws cli tools and configured correctly your home folder ~/.aws/config and ~/.aws/credentials
A typical ~/.aws/config should look like this:

```
[default]
region = eu-central-1
output = json

[profile source-profile-name]
region = eu-central-1
output = json

[profile other-profile-name]
source_profile = source-profile-name
role_arn = arn:aws:iam::12345678901:role/Administrator
region = eu-central-1
mfa_serial = arn:aws:iam::12345678901:mfa/virgilio.lino@moebel.de 
```

The credentials file instead can be created by running
```
aws configure
```

## Usage
. aws-assume other-profile-name
*please notice the . you need to explicitely write .<SPC>aws-assume because you need to source the result of the execution.*
## Todo

Currently I'm hardcoding one behaviour that could be easily dessumable from the config structure.

1. Make mfa_serial optional. I know its a good practice to use it, still, I'd like the script to work in any possible case.
Just check if there is the MFA ARN in the config then ask for the token.

