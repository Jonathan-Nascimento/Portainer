# Portainer
# Instalação do Portainer


* Portainer: Ferramenta para gerenciar container de forma gráfica utilizando o navegador.


1º - Crie um diretorio com o nome "Portainer" e entre no mesmo.



mkdir Portainer
cd Portainer



2º - Crie um um arquivo ".yaml" com as informações abaixo.




vim docker-compose.yaml

    version: '3'

    services:
        portainer:
        image: portainer/portainer-ce
        restart: always
        container_name: portainer
        volumes:
            - /var/run/docker.sock:/var/run/docker.sock
            - portainer_data:/data
        ports:
            - 9000:9000
            - 9443:9443
            - 8000:8000

    volumes:
        portainer_data:



3º Execute o arquivo ".yaml" para iniciar o contaienr Portainer.



docker-compose -f docker-compose.yaml up -d



4º Acesse o navegador e digite a url abaixo.



http://IP-HOST:9000



5º Na tela de login crie uma senha para user "admin"
