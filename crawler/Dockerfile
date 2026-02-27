FROM ruby:2.7-alpine

# Install dependencies
RUN apk add --no-cache \
    build-base \
    openssl-dev \
    git

WORKDIR /app/crawler

# Copy Gemfile
COPY Gemfile Gemfile.lock ./

# Install specific bundler version and gems
RUN gem install bundler:1.16.1 && bundle install

# Copy crawler code
COPY . .

# Run crawler
CMD ["bundle", "exec", "ruby", "crawler.rb"]
