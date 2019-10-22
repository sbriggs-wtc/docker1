FROM ruby
LABEL maintainer=sbriggs

RUN apt-get update &&\
    apt-get install -y build-essential libpq-dev nodejs sqlite3

ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app
ONBUILD EXPOSE 3000
ONBUILD RUN bundle install
ONBUILD RUN bundle exec rake db:migrate
ONBUILD RUN bundle exec rake db:seed

#docker build --tag ft-rails:on-build .
#docker run --name rnr -p 3000:3000 railsapp