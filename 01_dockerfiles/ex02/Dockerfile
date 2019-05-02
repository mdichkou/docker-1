FROM ruby
RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install nodejs  -y
RUN gem install rails bundler
RUN gem install rails
EXPOSE 3000
WORKDIR /opt/app/
COPY myapp3 .
ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed
