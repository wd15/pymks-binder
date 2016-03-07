# Try [PyMKS](https://pymks.org) using Docker

## Install Docker

Install Docker and run the Deamon. See
https://docs.docker.com/engine/installation/linux/ubuntulinux/ for
installation details.

    $ sudo service docker start

## Pull the Docker instance

Pull the Docker Instance from Dockerhub

    $ docker pull docker.io/wd15/pymks

## Test PyMKS

Test the build inside the instance.

    $ docker run -i -p 8888:8888 --net=host -t wd15/pymks:latest

and go to [http://localhost:8888](http://localhost:8888) and run
`import pymks; pymks.test` in a notebook.

## Build the Docker instance

Clone this repository and build the instance.

    $ git clone https://gist.github.com/d233c706bb493c91ecd5.git pymks-dockerize
    $ cd pymks-dockerize
    $ docker build --no-cache -t wd15/pymks:latest .

## Push the Docker instance

Create the repository in Dockerhub and then push it.

    $ docker login
    $ docker push docker.io/wd15/pymks:latest
