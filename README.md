
# Data Science server

> A server for your data science needs

## Important
The following steps require you to have AWS auhtentication to the account you will be interacting with. Please ensure you are logged in with that account, and your `$HOME/.aws/credentials` file has the correct authentication.

## Quickstart
You will be creating an instance with Python capabilities.

You will need to ensure you have a key-pair to be able to assume into this instance. Please ensure you have the `.pem` file associated with that key-pair. If you do not have a key-pair and need to create one, run the following in the root directory:
```
aws ec2 create-key-pair --key-name <key-pair-name-in-aws> --query 'KeyMaterial' --output text > <key-pair-name-file>.pem
```
__DO NOT PUSH THE PEM FILE INTO THE REMOTE REPO__, the git ignore should stop you from doing it automatically but please ensure you don't push this to the remote.

To create the instance, run the following from your root:
```
aws cloudformation create-stack --stack-name <name your stack> --template-body file://cf/template.yml --
```

## Assume into your instance
Once deployed, you can assume into your instance with SSH. 

#ADD PICTURES HERE

```ssh -i "<key-pair-name-file>.pem" ec2-user@<your-ec2-IP>```
