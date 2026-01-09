VERSION 0.8
FROM ruby:3.4.8
RUN gem install grpc

WORKDIR /kvclient

code:
    COPY client.rb .
    COPY github.com/earthly/earthly-example-proto:main+proto-rb/rb-pb/*.rb .

kv-ruby-client-docker:
    FROM +code
    SAVE IMAGE kv-ruby-client:latest

all:
    BUILD +kv-ruby-client-docker
