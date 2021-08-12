#  Install & configure Maven build tool on Jenkins
Maven is a code build tool which used to convert your code to artifact. this is widely used plugin to build in continuous integration

#### Follow this artical in **[YouTube](https://www.youtube.com/watch?v=wgfsVmHnAiM)**

#### Prerequisites
1. Jenkins server **[Get Help Here](https://www.youtube.com/watch?v=M32O4Yv0ANc)

#### Install Maven on Jenkins
Download maven packages https://maven.apache.org/download.cgi onto Jenkins server. In this case I am using /opt/maven as my installation directory
	- Link : https://maven.apache.org/download.cgi
```sh
    # Creating maven directory under /opt
  mkdir /opt/maven
  cd /opt/maven
  # downloading maven version 3.6.0
  wget https://mirrors.estointernet.in/apache/maven/maven-3/3.8.1/binaries/apache-maven-3.8.1-bin.tar.gz
  tar zvxf apache-maven-3.8.1-bin.tar.gz
  cd apache-maven-3.8.1
  ls
  cd bin
  ./mvn -version
  [root@ip-172-31-29-97 bin]# ./mvn -version
Apache Maven 3.8.1 (05c21c65bdfed0f71a2f2ada8b84da59348c4c5d)
Maven home: /opt/maven/apache-maven-3.8.1
Java version: 1.8.0_292, vendor: Red Hat, Inc., runtime: /usr/lib/jvm/java-1.8.0-openjdk-1.8.0.292.b10-1.el7_9.x86_64/jre
Default locale: en_US, platform encoding: UTF-8
OS name: "linux", version: "3.10.0-1062.12.1.el7.x86_64", arch: "amd64", family: "unix"
env
export PATH=/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin:/root/bin:/opt/maven/apache-maven-3.8.1/bin
echo $PATH
mvn -version
	
Setup M2_HOME and M2 paths in .bash_profile of user and add these to path variable
```sh
  vi ~/.bash_profile
  M2_HOME=/opt/maven/apache-maven-3.6.0
  M2=$M2_HOME/bin
  PAHT=<Existing_PATH>:$M2_HOME:$M2
```
#### Check point 
logoff and login to check maven version
Check maven version 
```sh
  mvn –version
```
So far you have completed installation of maven software to support maven plugin on jenkins console. Let's jump onto jenkins to complete remining steps. 

#### Setup maven on jenkins console
- Install maven plugin without restart  
  - `Manage Jenkins` > `Jenkins Plugins` > `available` > `Maven Invoker`

- Configure java path
  - `Manage Jenkins` > `Global Tool Configuration` > `Maven`

#### Next Steps

- [x] [Configure Users & Groups in Jenkins](https://youtu.be/jZOqcB32dYM)
- [x] [Secure your Jenkins Server](https://youtu.be/19FmJumnkDc)
- [x] [Jenkins Plugin Installation](https://youtu.be/p_PqPBbjaZ4)
- [x] [Jenkins Master-Slave Configuration](https://youtu.be/hwrYURP4O2k)
