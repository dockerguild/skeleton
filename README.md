# Docker containers skeleton

## Installation

    git clone git@github.com:dockerguild/skeleton.git myapp
    cd myapp
    rm -fr .git
    git init
    git remote add origin {your_repository}

## Configure proxy

Requirement : Nginx

Edit vhost `config/nginx/proxy.conf` and register it to nginx

    ln -s "${PWD}/config/nginx/proxy.conf" /etc/nginx/sites-enabled/myapp.conf
    service restart nginx

## Configure crontab

Edit vhost `config/crontab/crontab` and register it to crontab

    ln -s "${PWD}/config/crontab/crontab" "/etc/cron.d/myapp"

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

    bash /path_to_project/bin/console.sh dump
