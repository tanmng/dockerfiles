FROM alpine
LABEL maintainer="Tan Nguyen <tan.mng90@gmail.com>"

ENV TOR_PROXY_PORT 9050

# Install the tor binary
RUN apk add --no-cache tor

# Copy config file
COPY torrc /etc/tor/torrc

# Make sure to expose the damn port
EXPOSE ${TOR_PROXY_PORT}

ENTRYPOINT ["tor"]
