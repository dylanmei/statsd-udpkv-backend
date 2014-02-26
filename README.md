# StatsD UDP/KV Backend

This is a pluggable backend for [StatsD](https://github.com/etsy/statsd). It publishes to a remote UDP listener, such as a Splunk server, in key/value format.

*Counters* and *Timers* are supported. *Sets* and *Guages* are not implemented.

## Requirements

* [StatsD deamon](https://npmjs.org/package/statsd) versions >= 0.7.0.

## Installation

    $ cd /path/to/statsd
    $ npm install statsd-udpkv-backend

## Configuration

Add `statsd-udpkv-backend` to the list of backends in the StatsD configuration file:

    {
        backends: ["statsd-udpkv-backend"]
    }

Add the following basic configuration information to the StatsD configuration file.

    {
        udpkv: {
            host: "myhost",
            port: 50515,
            // addr: "myhost:50515",
            vars: { "Environment": "test" },
        }
    }

- `host` and `port` are required. `addr` **host:port** format is also ok.
- `vars` is an optional map of additional key/value pairs to send along.