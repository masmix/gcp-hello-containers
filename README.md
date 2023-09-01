# Project Name

Project for build simple docker image based on nginx for serving simple html static page 

## Table of Contents
- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
  - [Installation](#installation)
  - [Usage](#usage)
- [Docker](#docker)
  - [Building the Docker Image](#building-the-docker-image)
  - [Running the Docker Container](#running-the-docker-container)
  - [Customization](#customization)
- [Contributing](#contributing)
- [License](#license)

## Introduction

Project is useful for generating docker images for container based projects or labs.
It's targeting to use in the GCP cloud environment.
Level: beginner  

## Prerequisites

- Google Free Tier account or Google sandbox in Pluralsight configured
- Beginer knowdlege of 
    - Cloud Shell https://cloud.google.com/shell/docs/launching-cloud-shell
    - Cloud Shell Editor https://cloud.google.com/shell/docs/launching-cloud-shell-editor  
    - concept of containers (optional) https://cloud.google.com/learn/what-are-containers

## Create your docker artifact registry 

Folow this documentation to create docker artifact registry
https://cloud.google.com/artifact-registry/docs/docker/store-docker-container-images

## Dockerfile

In the root of project create Dockerfile file 

```dockerfile
FROM nginx
COPY html /usr/share/nginx/html
```

### Create html static page


```bash
mkdir html
touch index.html
```

### Index.html
Fill index.html file

```html
<!DOCTYPE html>

<html>

<head>
	<title>Simple web Development Template</title>

	<style>
		* {
			margin: 0;
			padding: 0;
		}

		.navbar {
			display: flex;
			align-items: center;
			justify-content: center;
			position: sticky;
			top: 0;
			cursor: pointer;
		}

		.background {
			background: black;
			background-blend-mode: darken;
			background-size: cover;
		}

		.nav-list {
			width: 70%;
			display: flex;
			align-items: center;
		}

		.logo {
			display: flex;
			justify-content: center;
			align-items: center;
		}

		.logo img {
			width: 180px;
			border-radius: 50px;
		}

		.nav-list li {
			list-style: none;
			padding: 26px 30px;
		}

		.nav-list li a {
			text-decoration: none;
			color: white;
		}

		.nav-list li a:hover {
			color: grey;
		}

		.rightnav {
			width: 30%;
			text-align: right;
		}

		#search {
			padding: 5px;
			font-size: 17px;
			border: 2px solid grey;
			border-radius: 9px;
		}

		.firstsection {
			background-color: green;
			height: 400px;
		}

		.secondsection {
			background-color: blue;
			height: 400px;
		}

		.box-main {
			display: flex;
			justify-content: center;
			align-items: center;
			color: black;
			max-width: 80%;
			margin: auto;
			height: 80%;
		}

		.firsthalf {
			width: 100%;
			display: flex;
			flex-direction: column;
			justify-content: center;
		}

		.secondhalf {
			width: 30%;
		}

		.secondhalf img {
			width: 70%;
			border: 4px solid white;
			border-radius: 150px;
			display: block;
			margin: auto;
		}

		.text-big {
			font-family: 'Piazzolla', serif;
			font-weight: bold;
			font-size: 35px;
		}

		.text-small {
			font-size: 18px;
		}

		.btn {
			padding: 8px 20px;
			margin: 7px 0;
			border: 2px solid white;
			border-radius: 8px;
			background: none;
			color: white;
			cursor: pointer;
		}

		.btn-sm {
			padding: 6px 10px;
			vertical-align: middle;
		}

		.section {
			height: 400px;
			display: flex;
			align-items: center;
			justify-content: center;
			max-width: 90%;
			margin: auto;
		}

		.section-Left {
			flex-direction: row-reverse;
		}

		.paras {
			padding: 0px 65px;
		}

		.thumbnail img {
			width: 250px;
			border: 2px solid black;
			border-radius: 26px;
			margin-top: 19px;
		}

		.center {
			text-align: center;
		}

		.text-footer {
			text-align: center;
			padding: 30px 0;
			font-family: 'Ubuntu', sans-serif;
			display: flex;
			justify-content: center;
			color: white;
		}
	</style>
</head>

<body>
	<nav class="navbar background">
		<ul class="nav-list">
			<div class="logo">
				<img src= "logo.png">
			</div>
			<li><a href="#web">Web Technology</a></li>
			<li><a href="#program">C Programming</a></li>
			<li><a href="#course">Courses</a></li>
		</ul>

		<div class="rightNav">
			<input type="text" name="search" id="search">
			<button class="btn btn-sm">Search</button>
		</div>
	</nav>

	<section class="firstsection">
		<div class="box-main">
			<div class="firstHalf">
				<h1 class="text-big" id="web">Web Technology</h1>
				<p class="text-small">
					HTML stands for HyperText Markup Language.
					It is used to design web pages using a markup
					language. HTML is the combination of Hypertext
					and Markup language. Hypertext defines the
					link between the web pages. A markup language
					is used to define the text document within tag
					which defines the structure of web pages.
					HTML is a markup language that is used by the
					browser to manipulate text, images, and other
					content to display it in the required format.
				</p>


			</div>
		</div>
	</section>

	<section class="secondsection">
		<div class="box-main">
			<div class="firstHalf">
				<h1 class="text-big" id="program">
					C Programming
				</h1>
				<p class="text-small">
					C is a procedural programming language. It
					was initially developed by Dennis Ritchie
					as a system programming language to write
					operating system. The main features of C
					language include low-level access to memory,
					simple set of keywords, and clean style,
					these features make C language suitable for
					system programming like operating system or
					compiler development.
				</p>


			</div>
		</div>
	</section>

	<section class="section">
		<div class="paras">
			<h1 class="sectionTag text-big">Java</h1>

			<p class="sectionSubTag text-small">
				Java has been one of the most popular
				programming language for many years.
				Java is Object Oriented. However it is
				not considered as pure object oriented
				as it provides support for primitive
				data types (like int, char, etc) The
				Java codes are first compiled into byte
				code (machine independent code). Then
				the byte code is run on Java Virtual
				Machine (JVM) regardless of the
				underlying architecture.
			</p>


		</div>

		<div class="thumbnail">
			<img src= "img.png" alt="laptop image">
		</div>
	</section>

	<footer class="background">
		<p class="text-footer">
			Copyright ©-All rights are reserved
		</p>


	</footer>
</body>

</html>

```


### Build and push container image

Run container
```shell
gcloud builds submit --region=europe-west1 --tag europe-west1-docker.pkg.dev/playground-s-11-c96fd4d9/sfdsaf/hello-nginx
```
Above tag value have to be adopted to your artifact registry and docker image tag variables.


### Test container image
Run container
```shell
docker run --name nginx -d -p 8080:80 europe-west1-docker.pkg.dev/playground-s-11-c96fd4d9/sfdsaf/hello-nginx
```

Verify container is up and running
```shell
docker ps 
```

Output should looks like this:

```shell
CONTAINER ID   IMAGE                                                                     COMMAND                  CREATED         STATUS         PORTS                  NAMES
e824dc4264a6   europe-west1-docker.pkg.dev/playground-s-11-c96fd4d9/sfdsaf/hello-nginx   "/docker-entrypoint.…"   4 seconds ago   Up 2 seconds   0.0.0.0:8080->80/tcp   nginx 
```

### Verify http service

```shell
curl localhost:8080
```

# Container debug

## Container crashed after start 

```shell
docker logs nginx
```

## Container is up and running but proble with http service

Go to bash shell inside container

```shell
docker exec -it nginx bash
```

Verify http service
```shell
curl localhost
```

# References - code sources 

index.html https://www.geeksforgeeks.org/design-a-web-page-using-html-and-css/

Dockerfile https://hub.docker.com/_/nginx
