1. Download oracle java 8

2. vi /etc/default/java
export JRE_HOME=/opt/jdk1.8.0_181
export PATH=$PATH:$JRE_HOME/bin

export JAVA_HOME=/opt/jdk1.8.0_181
export JAVA_PATH=$JAVA_HOME

export PATH=$PATH:$JAVA_HOME/bin

3. download Jboss EAP stable

4. lanjutkan perintah di bawah
$ sudo unzip [file Jboss] -d /opt/
$ cd /opt/
$ sudo ln -s jboss-as-7.1.1.Final/ jboss (OPTIONAL)
$ sudo adduser jboss (OPTIONAL) 
$ sudo chown -R jboss. /opt/jboss-as-7.1.1.Final/ /opt/jboss

$ sudo su - jboss
$ cd /opt/jboss/bin
$ ./add-user.sh

What type of user do you wish to add?
 a) Management User (mgmt-users.properties)
 b) Application User (application-users.properties)
(a): a

Enter the details of the new user to add.
Realm (ManagementRealm) : [Enter]
Username : jboss
Password : [Password]
Re-enter Password : [Password]
About to add user 'jboss' for realm 'ManagementRealm'
Is this correct yes/no? yes
Added user 'jboss' to file '/opt/jboss-as-7.1.1.Final/standalone/configuration/mgmt-users.properties'
Added user 'jboss' to file '/opt/jboss-as-7.1.1.Final/domain/configuration/mgmt-users.properties'

$ ./standalone.sh -Djboss.bind.address=0.0.0.0 -Djboss.bind.address.management=0.0.0.0 &
