FROM debian

ENV TS3SERVER_LICENSE=accept
EXPOSE 9987/udp 10011 30033
RUN useradd test
WORKDIR /home/test/teamspeak
RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y wget bzip2
RUN wget https://files.teamspeak-services.com/releases/server/3.6.1/teamspeak3-server_linux_amd64-3.6.1.tar.bz2
RUN tar -xvf teamspeak3-server_linux_amd64-3.6.1.tar.bz2
RUN rm teamspeak3-server_linux_amd64-3.6.1.tar.bz2
WORKDIR teamspeak3-server_linux_amd64
RUN chmod 777 ts3server_minimal_runscript.sh
USER test
CMD ["sh", "ts3server_minimal_runscript.sh"]
# docker build -t teamspeak.
# docker run --name teamspeak_serv -p 9987:9987/udp -p 10011:10011 -p 30033:30033 -e TS3SERVER_LICENSE=accept teamspeak
