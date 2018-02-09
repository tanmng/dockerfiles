# tor-sock-proxy

Run the [tor binary](https://www.torproject.org/) to set up a `SOCK5` proxy
which can work as a gateway to the Internet ಥ‿ಥ 

## Usage

Run the container (make sure to publish the port if you wish to use the proxy from your host)
and then set up your application (for Chrome you can use [Falcon
Proxy](https://chrome.google.com/webstore/detail/falcon-proxy/gchhimlnjdafdlkojbffdkogjhhkdepf?hl=en) to use the proxy).

Configuration of the container is default in `torrc`, you can find instruction
on how to config tor with the file in section **GENERAL OPTIONS** of [tor
manual](https://www.torproject.org/docs/tor-manual.html.en).

For custom config, you can either mount your config file at `/etc/tor/torrc` or
mount it wherever you wish and then specify its location using `-f` option to
the command.

### Environment variables
* `TOR_SOCK_PORT` - The port which `tor` proxy should listen on. Please make
    sure that this one match with the port you config in `TOR_CONFIG_FILE`:
    > `SocksPort 0.0.0.0:9050`

### Example

```bash
docker run -d --rm -p 9050:9050 nmtan/tor-sock-proxy
```
