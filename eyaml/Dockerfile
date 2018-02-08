FROM ruby:alpine
LABEL maintainer="Tan Nguyen <tan.mng90@gmail.com>"

RUN gem install hiera-eyaml && \
    mkdir /keys

ENTRYPOINT ["eyaml"]
