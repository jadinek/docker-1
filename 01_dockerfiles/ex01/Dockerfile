FROM debian:latest

RUN apt-get update &&\
    apt-get install wget -y bzip2

RUN wget https://files.teamspeak-services.com/releases/server/3.10.2/teamspeak3-server_linux_amd64-3.10.2.tar.bz2 &&\
    tar xvf teamspeak3-server_linux_amd64-3.10.2.tar.bz2
RUN cd teamspeak3-server_linux_amd64

ENV TS3SERVER_LICENSE=accept

WORKDIR /teamspeak3-server_linux_amd64
ENTRYPOINT ./ts3server_minimal_runscript.sh

#docker build ./ -t ex01
#docker run -it --name teamspeakServer -p 9987:9987/udp -p 30033:30033 -p 10011:10011 --rm ex01