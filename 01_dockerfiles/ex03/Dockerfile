FROM ubuntu

RUN apt-get update && \
		apt-get upgrade -y && DEBIAN_frontend=noninteractive && \
		apt-get install -y ca-certificates openssh-server apt-transport-https postfix curl
RUN apt-get update && apt-get install -y --no-install-recommends apt-utils
WORKDIR ./
RUN curl -LO https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh
RUN bash script.deb.sh
RUN apt-get update && EXTERNAL_URL="http://gitlab.example.com" apt-get install gitlab-ce
RUN apt update && apt install -y tzdata
RUN useradd gitlab
EXPOSE 443 80 22
RUN echo "root:123456" | chpasswd
RUN echo "PermitRootLogin yes" >> /etc/ssh/sshd_config
CMD /opt/gitlab/embedded/bin/runsvdir-start & EXTERNAL_URL="gitlab.example.com" && \
	service ssh start && \
	gitlab-ctl reconfigure && tail -f /dev/null
# docker build -t ex03 .
# docker run -it --rm -p 80:80 -p 21:22 --privileged ex03
