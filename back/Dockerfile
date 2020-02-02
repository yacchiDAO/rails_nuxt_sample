FROM ruby:2.6.3

RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs
RUN mkdir /rails_nuxt_sample
WORKDIR /rails_nuxt_sample
COPY Gemfile /rails_nuxt_sample/Gemfile
COPY Gemfile.lock /rails_nuxt_sample/Gemfile.lock
RUN bundle install
COPY . /rails_nuxt_sapmle
ADD . $HOME

CMD ["rails", "server", "-b", "0.0.0.0"]
