# Ruby container
FROM              ruby

# Install rails and create the rails application path.
RUN               apt-get update \
                  && apt-get upgrade -y \
                  && apt-get install -y \
                      build-essential \
                      sqlite3 \
                      nodejs
RUN               gem install rails \
                  && gem install bundler \
RUN               mkdir /opt/app

# # to test 
# " docker build -t ft-rails:on-build . "
# you need to install rails
# " rails new app"
# inside the app folder, create the Dockerfile_child, and build inside the app folder
# " docker build -t app -f Dockerfile_child . "
# " docker run -it -p 3000:3000 app "
# docker-machine ip Char
# in URL "http://192.168.99.102:3000/"
