FROM ruby
ONBUILD RUN apt-get update -y && apt-get install -y build-essential libpq-dev nodejs sqlite3
ONBUILD EXPOSE 3000
ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app
ONBUILD RUN bundle install
ONBUILD RUN bundle exec rake db:migrate
ONBUILD RUN bundle exec rake db:seed

# docker build -t ft-rails:on-build .
