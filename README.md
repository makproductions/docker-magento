## Docker for Magneto 2.3 / 2.4 

### Requirements
- Docker for mac
- Docker-sync

### Setup
Docker sync: https://docker-sync.readthedocs.io/en/latest/

## New Project Configuration
### 1. Setup Project Folder
1. Duplicate `_build` folder and  
### 2. Configure Docker-sync
1. Update all instances of your docker-sync volume name:
   1. docker-compose.yml
   2. docker-sync.yml
   3. docker-compose-dev.yml

Always use a unique name for a new project appended by `-sync`.     
E.g:  
`_build-sync` => `demo-sync`

### 2. Start Container
### 3. Composer Update
create a new composer.json file 
