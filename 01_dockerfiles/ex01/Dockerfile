FROM debian
EXPOSE 9987/udp
EXPOSE 10011
EXPOSE 30033
RUN useradd teamspeak
WORKDIR /home/teamspeak
RUN apt-get update && apt-get install -y && apt-get install wget bzip2 -y
RUN wget https://files.teamspeak-services.com/releases/server/3.6.1/teamspeak3-server_linux_amd64-3.6.1.tar.bz2
RUN tar xfvj teamspeak3-server_linux_amd64-3.6.1.tar.bz2
USER teamspeak
WORKDIR teamspeak3-server_linux_amd64
RUN touch .ts3server_license_accepted
ENTRYPOINT ["sh", "ts3server_minimal_runscript.sh"]
#docker run --name ts -it -p 9987:9987/udp -p 10011:10011 -p 30033:30033 -e --rm tserv
