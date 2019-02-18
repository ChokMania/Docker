FROM ubuntu

RUN apt-get update -y \
    && DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
      ca-certificates \
      openssh-server \
      apt-transport-https \
      curl \
      postfix

WORKDIR ./

RUN curl -LO https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh

RUN bash script.deb.sh

RUN apt-get update && EXTERNAL_URL="http://gitlab.example.com" apt-get install gitlab-ce

RUN apt update && apt install -y tzdata

EXPOSE 80 22 443

CMD /opt/gitlab/embedded/bin/runsvdir-start & EXTERNAL_URL="gitlab.example.com" && \
	gitlab-ctl reconfigure && \
	tail -f /dev/null

#docker build -t ex03 .
#docker run -it --rm -p 80:80 -p 21:22 --privileged ex03
