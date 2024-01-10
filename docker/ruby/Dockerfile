# Make Dockerfile next to Gemfile
# `docker run --rm -v "$PWD":/usr/src/app -w /usr/src/app ruby:3.0 bundle install` will generate a Gemfile.lock

FROM ruby:3.0

# throw errors if Gemfile has been modified since Gemfile.lock
RUN bundle config --global frozen 1

WORKDIR /usr/src/app

COPY Gemfile Gemfile.lock ./
RUN bundle install

COPY . .

CMD ["./project-name.rb"]
