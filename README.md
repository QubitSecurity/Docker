# Docker

### nginx docker container to host syslog

### 1. Create docker-compose.yml

#### 1-1. Download

    curl https://raw.githubusercontent.com/QubitSecurity/Docker/main/docker-compose.yml -o /home/docker/


### 2. Create dockerfile for Nginx
   

#### 2-1. Download

    curl https://raw.githubusercontent.com/QubitSecurity/Docker/main/nginx/dockerfile -o /home/docker/nginx/
    
    curl https://raw.githubusercontent.com/QubitSecurity/Docker/main/nginx/plura_docker.conf -o /home/docker/nginx/
    
    curl https://raw.githubusercontent.com/QubitSecurity/Docker/main/nginx/default.conf -o /home/docker/nginx/conf.d/

#### 2-2. Restart

    docker-compose down
    
    docker-compose up -d
    
    docker ps -a

#### 2-3. Check

    docker exec -it <> /bin/bash
    
    docker logs nginx
    
    docker restart <>

### 3. Install PLURA-agent

    echo ModPlura-Nginx > /etc/modplura
    echo 5.8.10 >> /etc/modplura
    echo /usr/sbin/nginx >> /etc/modplura
    echo /etc/nginx >> /etc/modplura
    touch /etc/.modplura

### 4. Check logging

    ls -al /var/log/plura/
    
    
### Reference

#### 1) https://docs.docker.com/config/containers/logging/configure/

#### 2) https://docs.docker.com/compose/

#### 3) https://www.w3schools.com/php/php_forms.asp

#### 4) https://www.tecmint.com/configure-custom-access-and-error-log-formats-in-nginx/

#### 5) http://blog.plura.io/?p=17883
