Облако Owncloud + онлайн редактор Collabora в связке с обратным прокси Traefik

На DNS-хостинге прописать 2 записи типа А:

    disk.hostname.com        ip
    collabora.hostname.com   ip
    
Далее

    git clone ${this repo}

    cd owncloud-collabora-traefik
    touch acme.json 
    chmod 600 acme.json

    mkdir docker-volumes
    mkdir docker-volumes/db
    mkdir docker-volumes/files
    
    
Создать свой .env файл с переменными окружения из .env-default и подправить значения на свои

    cp .env-default .env
    
Старт

    sudo docker-compose -f docker-compose.yml -f docker-compose-traefik.yml up -d

В браузере 
    
    disk.hostname.com
