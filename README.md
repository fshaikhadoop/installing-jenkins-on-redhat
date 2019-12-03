# installing-jenkins-on-redhat
Here we can learn how to install jenkins on redhat

There are also native binary packages available for Redhat, Fedora, and CentOS. 
First you need to set up the repository as follows:

$ sudo wget -O /etc/yum.repos.d/jenkins.repo http://jenkins-ci.org/redhat/jenkins.repo 
$ sudo rpm --import http://pkg.jenkins-ci.org/redhat/jenkins-ci.org.key

On a fresh installation, you may need to install the JDK: 

$ sudo yum install java-1.6.0-openjdk

Next, you can install the package as shown here: 

$ sudo yum install jenkins 

This will install the latest version of Jenkins into the /usr/lib/jenkins directory. The default Jenkins home directory will be in /var/lib/jenkins.

Now you can start Jenkins using the service command: $ sudo service jenkins start

Jenkins will now be running on the default port of 8080 (http://localhost:8080/).

Jenkins’s configuration parameters are placed in the /etc/sysconfig/jenkins file. However at the time of writing the configuration options are more limited than those provided by the Ubuntu package: you can define the HTTP port using the JENKINS_PORT parameter, for example, but to specify an application context you need to modify the startup script by hand. The principal configuration options are listed here:

JENKINS_JAVA_CMD The version of Java you want to use to run Jenkins

JENKINS_JAVA_OPTIONS Command-line options to pass to Java, such as memory options

JENKINS_PORT The port that Jenkins will to run on 
