FROM python:3.6
LABEL maintainer 'Cristiano Henrique Ferreira'

RUN useradd www && \
    mkdir /app && \
    mkdir /log && \
    chown www /log

#Definindo o usuário da nossa aplicação python
USER www
#Volumes servem como uma porta aberta de comunicação, 
#se eu quiser criar um canal entre dois containers, vou usar o caminho do volume
VOLUME /log 
#Quando o container for criado, nosso diretório principal será esse
WORKDIR /app
#Expondo as portas para builder o container, podendo ser remapeada e alinhada com o run.py
EXPOSE 8000

#No nosso ponto de entrada, entraremos nesse diretorio executando o CMD
ENTRYPOINT [ "/usr/local/bin/python" ]
CMD ["run.py"]

#$ docker container run -it -v c:/Projects/box/dev-build:/app -p 8080:8000 --name python-server  ex-build-dev
