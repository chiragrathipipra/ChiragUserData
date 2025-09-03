User Data for Dependencies installations for AMAZON Linux 2:-

#!/bin/bash
sudo yum -y update
sudo yum -y install ruby
sudo yum -y install wget

# Install AWS CodeDeploy agent for us-west-1 region

cd /home/ec2-user
wget https://aws-codedeploy-ap-south-1.s3.ap-south-1.amazonaws.com/latest/install
wget https://aws-codedeploy-us-west-1.s3.us-west-1.amazonaws.com/latest/install
sudo chmod +x ./install
sudo ./install auto
sudo yum install -y python-pip
sudo pip install awscli

# Check if CodeDeploy agent is running
sudo service codedeploy-agent status

# Enable and start CodeDeploy agent (if not running)
sudo service codedeploy-agent enable
sudo service codedeploy-agent start