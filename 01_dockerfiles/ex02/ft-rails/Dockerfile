FROM ruby:latest

RUN apt-get update && apt-get install -y build-essential&&\
    apt-get install -y sqlite3 libsqlite3-dev

ONBUILD RUN mkdir -p /opt/app
ONBUILD WORKDIR /opt/app

# Ensure gems are cached and only get updated when they change. This will
# drastically increase build times when your gems do not change.
ONBUILD RUN gem install rails bundler
ONBUILD RUN gem install rails

# Copy in the application code from your work station at the current directory
# over to the working directory.
ONBUILD COPY . .

ONBUILD EXPOSE 3000