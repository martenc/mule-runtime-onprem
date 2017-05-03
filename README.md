

# mule-runtime-onprem - Mule ESB Dockerfile
Docker Image packaging for MuleESB http://www.mulesoft.org
As of 5/3/17 only v.3.8.0 was available on Mule's nexus repo

### Usage

For a simple application using 8081 port as HTTP

```
docker run -d -name myMuleInstance -P -v ~/myAppsDir:/opt/mule/apps -v ~/myLogsDir:/opt/mule/logs mule-runtime-onprem
```

#### Noteworthy mount points

| Mount point       | Description                                                     |
|------------------ |-----------------------------------------------------------------|
|/opt/mule/apps     | Mule Application deployment directory                           |
|/opt/mule/domains  | Mule Domains deployment directory                               |
|/opt/mule/conf     | Configuration directory                                         |
|/opt/mule/logs     | Logs directory                                                  |


#### Exposed ports

| Port | Description                                                     |
|----- |-----------------------------------------------------------------|
| 8081 | Default HTTP port                                               |


This means only exposed port is 8081, if the application has other needs you should use `-p` rather than `-P`

```
-p 1234:1234
```

### What you still need to do to deploy to prod

#### How to install Enterprise License
https://docs.mulesoft.com/mule-user-guide/v/3.8/installing-an-enterprise-license

#### Connect runtime to our Anypoint Platform account
https://anypoint.mulesoft.com

#### Configure Maven for Jenkins, then whatever Jenkins side config
