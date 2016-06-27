# vagrant-jenkins
A vagrant (Vagrantfile) installation of Jenkins based on the Jenkins docker official image.

# start jenkins

```
$ vagrant ssh

vagrant@vagrant-ubuntu-trusty-64:~$ sudo su - jenkins
jenkins@vagrant-ubuntu-trusty-64:~$ . ~/.bashrc
jenkins@vagrant-ubuntu-trusty-64:~$ . ~/.bashrc_jenkins
jenkins@vagrant-ubuntu-trusty-64:~$ jenkins.sh
jenkins@vagrant-ubuntu-trusty-64:~$ jenkins.sh 
Running from: /usr/share/jenkins/jenkins.war
webroot: EnvVars.masterEnvVars.get("JENKINS_HOME")
Jun 27, 2016 2:16:54 AM winstone.Logger logInternal
INFO: Beginning extraction from war file
(...)
INFO: Jenkins is fully up and running
```

Using provision, the service can be started automatically. Jenkins can be registered as a service too.
