sudo curl -L "https://raw.githubusercontent.com/virgiliolino/aws-assume/master/aws-assume" -o /usr/local/bin/aws-assume

sudo chmod +x /usr/local/bin/aws-assume

I'm assuming you configured correctly your home folder ~/.aws/config and ~/.aws/credentials

just run
aws-assume profile-name

