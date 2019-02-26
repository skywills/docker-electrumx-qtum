
# docker-electrumx

[![Build Status](https://travis-ci.org/skywills/docker-electrumx-qtum.svg?branch=master)](https://travis-ci.org/skywills/docker-electrumx-qtum)
[![](https://images.microbadger.com/badges/image/skywills87/electrumx-qtum.svg)](https://microbadger.com/images/skywills87/electrumx-qtum)

> Run an Electrum server with one command

An easily configurable Docker image for running an Electrum server.

## Usage

```
docker run \
  -v /home/username/electrumx:/data \
  -e DAEMON_URL=http://user:pass@host:port \
  -e COIN=QTUM \
  -p 50002:50002 \
  skywills87/electrumx
```

If there's an SSL certificate/key (`electrumx.crt`/`electrumx.key`) in the `/data` volume it'll be used. If not, one will be generated for you.

You can view all ElectrumX environment variables here: https://github.com/kyuupichan/electrumx/blob/master/docs/environment.rst

### TCP Port

By default only the SSL port is exposed. You can expose the unencrypted TCP port with `-p 50001:50001`, although this is strongly discouraged.

### Version

You can also run a specific version of ElectrumX if you want.

```
docker run \
  -v /home/username/electrumx:/data \
  -e DAEMON_URL=http://user:pass@host:port \
  -e COIN=QTUM \
  -p 50002:50002 \
  skywills87/electrumx:v1.8.12
```

## License

MIT © Luke Childs
