FROM ruby:2.7.1
ARG WORKDIR

ENV LANG=C.UTF-8 \
    TZ=Asia/Tokyo

RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs

# rails 6ではyarnが必要
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - \
    && echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list
WORKDIR ${WORKDIR}
COPY Gemfile Gemfile
COPY Gemfile.lock Gemfile.lock
RUN bundle install
COPY . ${WORKDIR}
ADD . ${WORKDIR}

CMD ["rails", "server", "-b", "0.0.0.0"]
