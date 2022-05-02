FROM ruby:3.0.0

RUN apt-get update -qq && apt-get install -y nodejs postgresql-client

WORKDIR /data/app/

COPY Gemfile /data/app/
COPY Gemfile.lock /data/app/

RUN gem install bundler && bundle install

COPY entrypoint.sh /usr/bin/
RUN chmod +x /usr/bin/entrypoint.sh
ENTRYPOINT ["entrypoint.sh"]

EXPOSE 3000

CMD ["rails", "server", "-b", "0.0.0.0"]