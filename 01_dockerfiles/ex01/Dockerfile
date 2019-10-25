FROM debian:latest
RUN apt-get update &&\
    apt-get upgrade &&\
    apt-get install wget -y &&\
    apt-get install bzip2 -y &&\
    wget http://dl.4players.de/ts/releases/3.8.0/teamspeak3-server_linux_amd64-3.8.0.tar.bz2 &&\
    tar xvf teamspeak3-server_linux_amd64-3.8.0.tar.bz2 &&\
    cd teamspeak3-server_linux_amd64 &&\
    touch .ts3server_license_accepted

WORKDIR /teamspeak3-server_linux_amd64/
ENTRYPOINT ./ts3server_minimal_runscript.sh 

# docker run -it -p 9987:9987/udp <name>