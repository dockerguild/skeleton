# Docker containers skeleton

## Search and replace

    <MY_APP_NAME>           # Name of your application
    <MY_REPOSITORY>         # URL of your GIT repository
    <MY_PROJECT_PATH>       # Path of your application
    <IMAGE_NAME>            # Docker image name
    <IMAGE_VERSION>         # Docker image version
    <CONTAINER_DATA_PATH>   # Docker container data path
    <CONTAINER_PORT>        # Docker container port

## Installation

    git clone git@github.com:dockerguild/skeleton.git <MY_APP_NAME>
    cd <MY_APP_NAME>
    rm -fr .git
    git init
    git remote add origin <MY_REPOSITORY>

## Configure proxy

Requirement : Nginx

Edit vhost `config/nginx/proxy.conf` and register it to nginx

    ln -s "${PWD}/config/nginx/proxy.conf" /etc/nginx/sites-enabled/<MY_APP_NAME>.conf
    service nginx restart

## Configure crontab

Edit vhost `config/crontab/crontab` and register it to crontab

    ln -s "${PWD}/config/crontab/crontab" "/etc/cron.d/<MY_APP_NAME>"

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

## Crontab

For crontab usage

    bash /<MY_PROJECT_PATH>/bin/console.sh dump
