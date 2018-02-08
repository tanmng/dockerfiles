FROM node:alpine
LABEL maintainer="Tan Nguyen <tan.mng90@gmail.com>"

RUN npm install -g markdown-toc && \
    mkdir /source

WORKDIR /source
ENTRYPOINT ["markdown-toc"]
