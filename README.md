# Docker containers skeleton

Starter kit, fork me for use.

## Requirements

 - Nginx

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
