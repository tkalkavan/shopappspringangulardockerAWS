
# ****DOCKERIZED Spring Boot + Angular 9 CRUD + MongoDB + Tutorial on AWS****



### Install the most recent Docker Engine package on Amazon Linux 2
```bash 
sudo amazon-linux-extras install docker
```
Go to instance summary tag and get Public IPv4 DNS address which my case:
You can create elastic IP and use it as static IP if you want to make your application more efficient.

```bash                           
 ec2-34-221-43-28.us-west-2.compute.amazonaws.com
```

On Filezilla or any other FTP program, Select SFTP protocol


![Alt text]( https://i.ibb.co/F06ddSc/ftp.png "FTP configuration")

Upload the files. For spring boot application  you are going to upload jar and for angular you 
can upload angular folder.

## Dockerfile/Image/Container

- **Image**: It's a sharable file that includes commands to assemble an image.
- **Container**: is a simple instance of an image. It is an executable image that runs on OS.
- **Dockerfile**: Recipe for Docker image. It defines how to create an application image. Build to the docker image.
  


## Docker compose

- Used for defining and running wat multi-container Docker applications.
- Configuration for containers to allow link and run together.
- It describes how the container is run in OS.
- It's the flexible and efficient way to construct your application

## Docker commands
To run our application docker-wise, we need to perform discrete commands.  To do this, we will run a command to create our application image.
To do so go to the application root, which you defined Dockerfile for song application, song-app-container namely

```sh
sudo service docker start
```

# Ready to go building our images

```sh
cd YOUR_APPLICATION_FOLDER
sudo docker build -t song-app-container .
```
Here **song-app-container** is the name of your container in which docker-compose will match using this name.
By using this command we built our spring application.
The next step is creating the angular image

```sh
cd YOUR_APPLICATION_FOLDER\angular
sudo docker build -t angular-service .
```
You can check created images with the below command:

```sh
 docker image ls
```

After that, we are ready to run our application with help of compose

```sh
docker-compose up
```

# Here we go:

Hit the URL to see the result. In my case, I assigned elastic IP for simplicity.

http://44.228.201.104:4200/listOfSongs 

![Alt text](https://i.ibb.co/RCWf21V/awsapp.png "Running dockerized AWS application")

