# Checkpoint 5 Submission

- **COURSE INFORMATION: NDD**
- **STUDENT’S NAME: Kinod Lakdinu Melewa Thanthrige**
- **STUDENT'S NUMBER: 130349210**
- **GITHUB USER_ID: 130349210-myseneca**
- **TEACHER’S NAME: Atoosa Nasiri**

### Table of Contents
1. [Part A - Containerize an application](#header1)
2. [Part B - Share the application](#header2)
3. [Part C - Persist the DB](#header3)
4. [Part D - Multi container apps](#header4)

#

### **Part A - Containerize an application**

- **Question 1 - If you run docker build -t getting-started . for a second time, the build time will be different from first time, why? Why the number of steps are also different? Explain your answers in detail.**

Docker employs a caching mechanism to optimize the process of building images. When a new image is built, Docker executes the instructions specified in the Dockerfile, which outlines the steps for creating the image. These instructions are executed using the `docker build` command and are stored in Docker's cache. When `docker build` is run again, Docker checks the cache for each step in the Dockerfile. If a step remains unchanged, Docker utilizes the intermediate image from the cache, resulting in a faster build process. However, if a step has been modified, Docker invalidates the cache for that step and re-executes it, along with all subsequent steps, thereby prolonging the build process.

- **Question 2 - What does -t flag do? If you do not use it what is the error? embed the error in your answer.**

The **-t  flag** in the ` docker build ` command basically specifies a name and an optional tag for the container image creation. The name and tag is used as a reference to the image.

If the user doesn't use the **-t  flag**, the user will be presented with an error as such:

```
$ docker build .
"docker build" requires exactly 1 argument.
See 'docker build --help'.
```

- **Question 3 - Run docker build -t getting-started . a few times and then run docker image ls to get the list of your images, why do you still one image listed even though you have tried building image many times?**

When we execute the `docker build -t getting-started .` command multiple times, each build generates a new image. However, when we check the images using the `docker image ls` command, only one image is displayed. This is because Docker takes advantage of the cached instructions from the initial build and reuses them, rather than creating new ones for each subsequent build.


- **Question 4 - What are -d and -p flags? What does each flag do? Start another git bah or wsl terminal and run docker run -p 1000:3000 getting-startedin it, Notice that -d is missing. What is the output?Embed it in your submission. Explain why this happened?**

**-d flag** -  This means the "detached" mode that will instruct the Docker to run the container in the background.

**-p flag** - This means "publish ports" that map network ports between the Docker host and the container.

When the user run the ` docker run -p 1000:3000 getting-started ` without the -d flag, the container will run in an "attached mode" which means it will run in the foreground. 

```
Using sqlite database at /etc/todos/todo.db
Listening on port 3000
```

- **Question 5 - The previous question has created a new container with your app running in it. Which port in localhost must be used to reach it?**

localhost:1000


- **Question 6 - Run docker ps and embed the output in your answer. If you have completed previous questions, you should have at least two containers running in your system. What is their difference? Can you explain how and why this was necessary?**

The main difference between the two containers is their port mappings. Port **3000** inside the container is mapped to port **1000** on the localhost. To access this container from the localhost, user should use ` localhost:1000 ` and Port **3000** inside the container is mapped to port **3000** on the localhost. To access this container from the localhost, user should use ` localhost:3000 `.

- **Question 7 - How long did it take to create the image after you updated the code? It is still shorter than the first time you did it, why?**

After updating the code, the image creation process only took a few seconds, which is shorter than the initial build. This is because Docker reused the cached instructions for image creation, resulting in a quicker build time.

- **Question 8 - What is the error message you get when you try to run the app container? Embed the error in your submission and explain why do you get this error at all?**

``` 
3000:3000 getting-started
206eb4fa59da6840f6277bd900479403c74045f33ff7083f727abd7a8458d9c9
docker: Error response from daemon: driver failed programming external connectivity on endpoint sleepy_cannon (7831963a96fff2bb3afbfb8489776a897360f1eb5d6ee5fabb11934282b3ea30): Bind for 0.0.0.0:3000 failed: port is already allocated.
```

- **Question 9 - Embed a screenshot of your app in your submission.**
<img src="Part A - Q9.png" alt="Question 9" title="Question 9">

#
### **Part B - Share the application**

- **Images from DockerHub**
<img src="B - 1.png" alt="Images from Docker Hub" title="Images from Docker Hub">

- **Deployed app page**
<img src="B - 2.png" alt="Deployed app page" title="Deployed app page">

#
### **Part C - Persist the DB**
```
$ docker volume inspect todo-db
[
    {
        "CreatedAt": "2023-06-13T01:59:58Z",
        "Driver": "local",
        "Labels": null,
        "Mountpoint": "/var/lib/docker/volumes/todo-db/_data",
        "Name": "todo-db",
        "Options": null,
        "Scope": "local"
    }
]
```
#
### **Part D - Multi container apps**
- **mysql> SHOW DATABASES;**
```
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
| todos              |
+--------------------+
5 rows in set (0.00 sec)
```

- **dig mysql**
```
c71276df4a87  ~  dig mysql

; <<>> DiG 8.0.33.1 <<>> mysql
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 40310
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 0

;; QUESTION SECTION:
;mysql.                         IN      A

;; ANSWER SECTION:
mysql.                  600     IN      A       172.22.0.1

;; Query time: 99 msec
;; SERVER: 127.0.0.11#53(127.0.0.11) (UDP)
;; WHEN: Sun Jun 12 22:30840 UTC 2023
;; MSG SIZE  rcvd: 44
```

- **mysql> SELECT * from todo_items;**
```
+--------------------------------------+----------------+-----------+
| id                                   | name           | completed |
+--------------------------------------+----------------+-----------+
| bb4907d2-fab9-4650-9c61-c3130ea3c9b5 | Be Positive!!! |         0 |
| 8b0b3ad1-4359-43b9-8fab-04dc91cdca3d | Do assignments |         0 |
+--------------------------------------+----------------+-----------+
2 rows in set (0.00 sec)

```
#
Thank you :)