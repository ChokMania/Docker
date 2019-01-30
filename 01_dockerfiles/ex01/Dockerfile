FROM debian
MAINTAINER Julien Dumay <judumay@student.42.fr>

WORKDIR /home/teamspeak

EXPOSE 9987:9987/udp 10011:10011 30033:30033

ENV TS3SERVER_LICENSE=accept

RUN apt-get update && apt-get upgrade -y && apt-get install -y wget bzip2 && \
	wget http://dl.4players.de/ts/releases/3.0.13.8/teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2  && \
		tar xvf *.tar.bz2

WORKDIR teamspeak3-server_linux_amd64
ENTRYPOINT ["install_ts3-server.sh"]

#ENTRYPOINT sh script_ts.sh

#docker build -t teamspeakerimg .
#docker run --rm -p 9987:9987/udp -p 10011:10011 -p 30033:30033 teamspeakerimg
