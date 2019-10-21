FROM debian
LABEL maintainer=sbriggs
WORKDIR /teamspeakserver3
EXPOSE 9987/udp 10011 30033
RUN apt-get update &&\
    apt install wget bzip2 -y &&\
    wget https://files.teamspeak-services.com/releases/server/3.9.1/teamspeak3-server_linux_amd64-3.9.1.tar.bz2 &&\ 
    tar -xjf teamspeak3-server_linux_amd64-3.9.1.tar.bz2 &&\
    touch teamspeak3-server_linux_amd64/.ts3server_license_accepted

CMD sh teamspeak3-server_linux_amd64/ts3server_minimal_runscript.sh start

#docker build --tag ex01 .
#docker run -itd --name tss -p 9987:9987/udp -p 10011:10011 -p 30033:30033 ex01
#docker logs tss