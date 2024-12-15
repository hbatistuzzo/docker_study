
<div align="center">
  	<img align='left' width=200px alt='docker' <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/docker/docker-original-wordmark.svg"/>
    <img align="center" alt="postgres" width="200px" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original-wordmark.svg" />
    <img align="right" alt="python" width="200px" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original-wordmark.svg" />
</div>

<br>

---

<br>

This repository compiles my Docker studies from a number of different sources: coursera/udemy/free-data-camp courses, along with myriad tutorials.

__*but why?*__
* It follows that from a traditional data analysis learning path comes a point where data engineering skills become not only useful, but necessary: as the different steps of data manipulation morph into an ETL process, the pipeline emerges. This pipeline _will_ leak, bugs _will_ crawl inside, and now we need tools to make sure that the ~~spice~~ data flows smoothly.

__*but how?*__
* With a number of different tools. But in particular, on the subject of infrastructure, with Docker and containerization.

---

## Docker Commands

*docker run*
* start a container from an image. Creates an instance of whatever application is needed. If the image is not present in the host, it will pull from the docker hub (this only happens a single time, however).

*docker ps*
* list all running containers and info: the name of the image we've used to run the containers, the current status and the newly created id and name of the container (the funky ones such as sad_tamagoya).
* ps -a outputs everything (running or not)

*docker stop sad_tamagoya*
* to stop we need either the id or the name, as above

*docker rm sad_tamagoya*
* this will remove the container, so it doesn't consume resources

*docker images*
* list of available images and their sizes

*docker rmi ubuntu*
* this will remove the image. No containers must be running from that image before trying to remove an image

*docker pull command*
* will only download the image, but not run it automatically (as doecker run does)

<br>

---

> [!TIP]
> Bear in mind the container only lives for as long as the process inside it is alive. Just using docker run whatever might download the image if it's not already there, but it immediately shifts the status to "exited".

---

*docker exec _sad_tamagoya_ cat /etc/hosts*
* this will print the contents from this etc/hosts file. It executes a command on the container.

and finally

*docker run -d whatever*
* this will run the container on the background, in detached mode, which will leave the prompt still useful.

if you want to attach back the container, on a later date, just run:

*docker attach "id of the container"

