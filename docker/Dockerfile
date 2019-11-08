# To Do, move to alpine distribution to reduce bundle size
FROM ruby:2.6.3

COPY Gemfile* /tmp/
WORKDIR /tmp
RUN bundle install

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash - \
   && apt install -y nodejs

ENV app /app
RUN mkdir $app
WORKDIR $app
ADD . $app

ENTRYPOINT ["./entrypoint.sh"]
