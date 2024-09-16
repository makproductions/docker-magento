## Docker for Magento 2.3 / 2.4 

### Requirements
- Docker for mac
- Docker-sync (https://docker-sync.readthedocs.io/en/latest/)

## First Time Setup
#### 1. Shortcut Scripts (/scripts)
To set up shortcut scripts as global:  
Run the setup bash file as sudo user : `sudo ./setup`

#### 2. Build Generic containers
Run the `start` script in the root directory of the project to launch **shared** containers.
The following containers are shared between all php containers:
- DB (mariadb)
- elasticsearch
- phpmyadmin
- redis
- redis-session
- mailhog

---
## Project Setup 

### 1. Project Folder
1. Duplicate `_build` folder with a new name in the same directory (73 or 81).    

### 2. Configure Docker-sync
1. Update all instances of docker-sync volume name in the following files:
   1. docker-compose.yml
   2. docker-sync.yml
   3. docker-compose-dev.yml

Always use a unique name for each project appended by `-sync`.     
E.g: `_build-sync` >> `demo-sync`

### 3. Network
Rename network in `docker-compose.yml` file in your project, to reflect the following format:
`{ROOTFOLDER}_main-network`

> **Hint**: You can run `docker network ls` to find the full name of your `{ROOTFOLDER}_main-network`

### 4. Starting Container
2. Run `composer update` command

---
### Shortcut Script commands

| Commands      | Description                                                                                            | Options & Examples |
|---------------|--------------------------------------------------------------------------------------------------------|-------------------|
| `start`       | Start the container in your current project directory                                                  | `start`           |
| `stop`        | Stop the containers in your current project directory                                                  | `stop`            |
| `shell`       | Access your container as www-data user                                                                 | `shell`       | |
| `root`        | Access your container as Root user                                                                     | `root`            | |
| `dbimport`    | Predefined Script to import a new Database. A db.sql file must exist in your project directory         | `root`            | |
| `configHttps` | Setup SSL Certificates, Maps DB URL's to .htaccess file for website scope                              | `root`            | |
| `kill`        | Stops containers and removes containers, networks, volumes, and images created to the specific project |                   |
| `magento`     | Use the power of the Magento CLI                                                                       |                   |
| `n98`         | Use the Magerun commands as you want                                                                   |                   |
| `grunt-init`  | Prepare to use Grunt                                                                                   |                   |
| `grunt`       | Use Grunt specifically in your theme or completely, it'll do the deploy and the watcher.               | `grunt luma`      |
| `xdebug`      | Enable / Disable the XDebug                                                                            |                   |
| `composer`    | Use Composer commands                                                                                  | `composer update` |