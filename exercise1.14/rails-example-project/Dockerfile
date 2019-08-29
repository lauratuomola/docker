FROM ruby:2.6.0

WORKDIR /mydir

RUN apt-get update && apt-get install -y nodejs
RUN gem install bundler
COPY . .
RUN bundle install
RUN rails db:migrate

EXPOSE 3000

CMD ["rails", "s"]