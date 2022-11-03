# SpeedokuRoyaleServer | Production environment

## Installation - Metropolia EDUCloud - Part 1

1. Make sure that you are using Metropolia VPN.
2. Sign into [Metropolia Educloud](https://educloud.metropolia.fi/).
3. Navigate to services.
4. Order Centos 7 x64 with basic install where IP address setup is done.
5. Wait for the confirmation email from [Metropolia Helpdesk](helpdesk@metropolia.fi)

## Installation - Metropolia EDUCloud - Part 2

**Remember** You can access the IP address, password for root user and
other useful information through the confirmation email!

Props for parts 3 - 9 goes to [SysAdminXpert](https://sysadminxpert.com/how-to-install-jenkins-on-centos-7-or-rhel-7/)!

1. Make sure that you are using Metropolia VPN.
2. Access the server via ssh with root acconut from terminal with following command\
   `ssh root@<IP ADDRESS HERE>`
3. Install Java SDK 8 with following command\
   `sudo yum install java-1.8.0-openjdk-devel`
4. Install Jenkins Repository with following commands\
   `curl --silent --location http://pkg.jenkins-ci.org/redhat-stable/jenkins.repo | sudo tee /etc/yum.repos.d/jenkins.repo`\
   `sudo rpm --import https://jenkins-ci.org/redhat/jenkins-ci.org.key`
5. Install Stable Jenkins with following command\
   `sudo yum install jenkins`
6. Start the Jenkins service and auto start on boot with following commands\
   `sudo systemctl start jenkins`\
   `sudo systemctl enable jenkins`
7. Check that Jenkins is running with following command\
   `systemctl status jenkins`
8. Configure the firewall and allow 8080 port
   `sudo firewall-cmd --permanent --zone=public --add-port=8080/tcp`
   `sudo firewall-cmd --reload`
9. Open jenkins in `http://<IP ADDRESS HERE>:8080` and follow the jenkins setup.

After all this you should be done!
   
