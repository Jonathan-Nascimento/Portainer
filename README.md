# Portainer
# Portainer



* Portainer: Ferramenta para gerenciar container de forma gráfica utilizando o navegador.

1º - Crie um diretorio com o nome "Portainer" e entre no mesmo.

<syntaxhighlight lang="bash">
mkdir Portainer
cd Portainer
</syntaxhighlight>

2º - Crie um um arquivo ".yaml" com as informações abaixo.


<syntaxhighlight lang="bash">
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
</syntaxhighlight>


3º Execute o arquivo ".yaml" para iniciar o contaienr Portainer.

<syntaxhighlight lang="bash">
docker-compose -f docker-compose.yaml up -d
</syntaxhighlight>

4º Acesse o navegador e digite a url abaixo.

<syntaxhighlight lang="bash">
http://IP-HOST:9000
</syntaxhighlight>

5º Na tela de login cire uma senha para user "admin"