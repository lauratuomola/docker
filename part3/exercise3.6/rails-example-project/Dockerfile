FROM ruby:2.6.0-alpine

WORKDIR /mydir

RUN apk add --no-cache build-base nodejs sqlite-dev tzdata && \
    gem install bundler

COPY . .

RUN bundle install && rails db:migrate

EXPOSE 3000

CMD ["rails", "s"]
