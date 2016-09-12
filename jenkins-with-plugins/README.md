
### Description
jenkins with nodejs slave

### Usage
Use it with docker-compose    

### Build

    docker build -t registry.cn-hangzhou.aliyuncs.com/zhijin/jenkins:plugins .

```
jenkins:
    image: 'registry.aliyuncs.com/acs-sample/jenkins:latest'
    ports:
        - '8080:8080'
        - '50000:50000'
    volumes:
        - '/var/lib/docker/jenkins:/var/jenkins_home'
    privileged: true
    restart: always
    labels:
        aliyun.scale: '1'
        aliyun.probe.url: 'tcp://container:8080'
        aliyun.probe.initial_delay_seconds: '10'
        aliyun.routing.port_8080: jenkins
    links:
        - slave-nodejs

slave-nodejs:
    image: 'registry.aliyuncs.com/acs-sample/jenkins-slave-dind-nodejs'
    restart: always 
    labels:
        aliyun.scale: '1'
```
