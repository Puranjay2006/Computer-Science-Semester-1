# What is Docker and Nginx?

Docker and Nginx are two powerful tools commonly used in web development and deployment. Let's break down what each one does:

**Docker:**

* **Containerization platform:** Docker is a platform that allows you to package applications and their dependencies into self-contained units called containers.
* **Isolation and portability:** Containers provide a consistent environment, ensuring that your application runs the same way regardless of the underlying system. This makes it easier to deploy and scale applications.
* **Efficient resource utilization:** Containers are lightweight compared to virtual machines, allowing you to run more applications on a single host.

**Nginx:**

* **High-performance web server:** Nginx is a popular open-source web server known for its speed and efficiency.
* **Reverse proxy:** Nginx can act as a reverse proxy, load-balancing requests across multiple backend servers.
* **Static content serving:** It's excellent at serving static content like HTML, CSS, and JavaScript files.
* **Load balancing:** Nginx can distribute traffic across multiple web servers based on various load-balancing algorithms.

**How Docker and Nginx work together:**

1. **Containerizing the application:** You create a Dockerfile that defines the environment and dependencies required for your application. Docker builds this into a container image.
2. **Running the container:** You run the container image using the `docker run` command. This starts your application inside the container.
3. **Nginx as a reverse proxy:** You configure Nginx to act as a reverse proxy, forwarding requests to the containerized application. Nginx can handle load balancing, SSL termination, and other tasks.

**Key benefits of using Docker and Nginx together:**

* **Simplified deployment:** Docker containers provide a consistent environment, making it easier to deploy applications across different systems.
* **Scalability:** You can easily scale your application by running multiple containers and using Nginx for load balancing.
* **Efficient resource utilization:** Docker containers are lightweight, allowing you to run more applications on a single host.
* **Improved performance:** Nginx is a high-performance web server, providing fast response times and efficient handling of requests.

_By combining Docker and Nginx, you can create a robust and efficient web infrastructure that is easy to manage and scale._

___

## Steps to host a website using Docker and Nginx:

1. Login to your AWS account, download your passkey and launch the EC2 instance.  
2. Launch PuTTY, add the IP address from the instance, add the key pair file, and open the PuTTY terminal.
3. Log in to the OS by writing "ubuntu".

- Now, you have to install Docker on your operating system. Use the following command to do so:

```bash
curl -sL https://github.com/ShubhamTatvamasi/docker-install/raw/master/docker-install.sh | bash
```

- Type the following command to avoid using ``sudo`` always:

```bash
newgrp docker
```

- Then, type: (This provides a list of the Docker containers on your machine)

```bash
docker ps
```

- You can check your docker version by typing:

```bash
docker --version
```

- Now, to use ``Nginx`` in our container, use the following commands: (Run one first, then the other after it.)

```bash
docker pull nginx
```

```bash
docker run --name docker-nginx -p 80:80 nginx
```
___

### Steps to create your website:

- Use the following command to stop the container from running:

```bash
ctrl + c
```

- Use the following command to reveal that the Docker container has been exited:

```bash
docker ps -a
```

- Use the following command to see new information about the container:

```bash
docker ps
```

- Use following command to stop the container:

```bash
docker stop docker-nginx
```

- Then, remove the default Nginx page and create a new custom HTML file using the following commands:

```bash
docker rm docker-nginx
```

```bash
mkdir -p ~/docker-nginx/html
```

- Now, navigate to file created:

```bash
cd ~/docker-nginx/HTML
```

- Next, create a ``index.html`` and write a HTML Code on ``vim`` code editor:

```bash
vi index.html
```

- Now, write your own HTML Code and save the file. Then, connect the file to the instance:

```bash
docker run --name docker-nginx -p 80:80 -d -v ~/docker-nginx/html:/usr/share/nginx/html nginx
```

- _Now, go to your AWS EC2 Dashboard, copy the public IP Address of your current Instance, and paste it into the search box of the browser._<br> 
- _Once you press Enter, you should successfully be able to see your webpage._
