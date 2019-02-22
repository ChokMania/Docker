FROM debian

RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install -y openjdk-8-jre-headless screen \
	wget
RUN mkdir /etc/minecraft
WORKDIR /etc/minecraft
RUN wget -O /etc/minecraft/minecraft_server.jar https://launcher.mojang.com/v1/objects/3737db93722a9e39eeada7c27e7aca28b144ffa7/server.jar
RUN chmod +x minecraft_server.jar
COPY files/eula.txt .
EXPOSE 25566
CMD java -Xms1024M -Xmx1536M -jar /etc/minecraft/minecraft_server.jar -o true
#docker run -it -p 25565:25565 mcserv
