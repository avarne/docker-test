## Write a Dockerfile (CentOS 6) to install the following in a Docker continer
1.Python 2.7

2.MongoDB - any version

3.Apache tomcat 7 - running on port 8080

4.Please include comments at every command explaining what it does.

5.Write the command to run the Dockerfile such that once the container boots, apache tomcat's home page is accessible from the host on port 7080.

### Solution
#### For building image from Dockerfile use following command

```sh
docker build -t centos6_python .
```

#### For starting container use following command
```sh
docker run -it centos6_python
```

#### Known Issue
 As of now tomcat service is not starting by default. 
