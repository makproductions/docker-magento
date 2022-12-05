## Docker for Magento 2.3 / 2.4 

### Requirements
- Docker for mac
- Docker-sync (https://docker-sync.readthedocs.io/en/latest/)

## First Time Setup
#### Shortcut Scripts (/scripts)
To set up shortcut scripts you have 2 options:
1. Run `setup` bash file as sudo user : `sudo ./setup`
2. Create a symbolic link for every new project : `ln -s ../../scripts /run`

#### Network
4. Rename your network in `docker-compose.yml` file to reflect the following format:
`ROOTFOLDER_main-network`
---
## New Project Configuration
### 1. Build Generic containers
This setup shares containers for the following services between all php containers:
- DB (mariadb)
- elasticsearch
- phpmyadmin
- redis
- redis-session
- mailhog

1. Run the `start` script in the root folder to launch shared containers. 

### 2. Setup Project Folder
1. Copy `_build` folder and paste it with your project name  

### 3. Configure Docker-sync
1. Update all instances of docker volume name:
   1. docker-compose.yml
   2. docker-sync.yml
   3. docker-compose-dev.yml

Always use a unique name for each project appended by `-sync`.     
E.g:  
`_build-sync` >> `demo-sync`

### 2. Start Container
### 3. Composer Update
1. Create a new composer.json file
2. Run `composer update` command
