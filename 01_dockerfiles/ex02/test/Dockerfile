FROM ruby
ONBUILD RUN apt-get update -y && apt-get install -y mysql-client build-essential libpq-dev nodejs sqlite3
ONBUILD RUN gem install rails
ONBUILD ENV RAILS_ENV=development
ONBUILD EXPOSE 3000
ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app
ONBUILD RUN bundle install
ONBUILD RUN bundle exec rake db:migrate
ONBUILD RUN bundle exec rake db:seed

# docker build -t ft-rails:on-build .
# http://192.168.99.100:3000/
# https://bundler.io/man/bundle-install.1.html
# https://guides.rubyonrails.org/command_line.html#rails-dbconsole
