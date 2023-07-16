Build and Deploy nodejs application on EC2 instance - Freestyle
Pre-requisites
A Jenkins server
A EC2 instance (Application server) and deploy node.js
Setup nodejs packages on jenkins (needed for build) and application server (needed to deploy)
Enable nodejs packages on Linux server

curl -sL https://rpm.nodesource.com/setup_15.x | bash -
install development tools.

yum groupinstall 'Development Tools'
Install nodejs

yum -y install nodejs
Setup Jenkins job

Fork nodejs applicaton onto your repository
Github URL: https://github.com/ravdy/nodejs.git

Using simple "hello world" application from the nodejs.org website

On Jenkins GUI
Create the new FreeStyle Project
Git URL - https://github.com/ravdy/nodejs.git
BUILD --> Execute Shell npm install

npm install
tar czf easyio.tar-$BUILD_NUMBER.gz node_modules main.js package.json public LICENSE
To Deploy on nodejs application server
