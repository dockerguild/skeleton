# Docker containers skeleton

## Search and replace

    <MY_APP_NAME>           # Name of your application
    <MY_REPOSITORY>         # URL of your GIT repository
    <MY_PROJECT_PATH>       # Path of your application
    <IMAGE_NAME>            # Docker image name
    <IMAGE_VERSION>         # Docker image version
    <CONTAINER_DATA_PATH>   # Docker container data path
    <CONTAINER_PORT>        # Docker container port

## Create new project

    git clone git@github.com:dockerguild/skeleton.git <MY_APP_NAME>
    cd <MY_APP_NAME>
    rm -fr .git
    git init
    git remote add origin <MY_REPOSITORY>

## Installation

    make install

## Usage

Start containers

    make start

Restart containers

    make restart

Down containers

    make down

Update containers

    make update

## Backup

**Before your must configure** `.make/filesystem` and `.make/mysql` according to your use.

**You must also set up an external backup system !**

Dump containers files

    make filesystem/dump

Dump mysql database

    make mysql/dump

Restore containers files

    make filesystem/restore

Restore mysql database

    make mysql/restore
