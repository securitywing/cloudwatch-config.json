# cloudwatch-config.json to enable disk space monitoring of EC2
1. Install the cloudwatch agent
sudo yum -y install amazon-cloudwatch-agent

2. create a config.json file in the following location, and paste the content of this repo.

/opt/aws/amazon-cloudwatch-agent/bin/config.json

3. Run the agent
sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl -a fetch-config -m ec2 -s -c file:/opt/aws/amazon-cloudwatch-agent/bin/config.json

4. check the status of the agent
systemctl enable amazon-cloudwatch-agent