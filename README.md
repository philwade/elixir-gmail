elixir-gmail [![Build Status](https://secure.travis-ci.org/craigp/elixir-gmail.png?branch=master "Build Status")](http://travis-ci.org/craigp/elixir-gmail) [![Coverage Status](https://coveralls.io/repos/craigp/elixir-gmail/badge.svg?branch=master&service=github)](https://coveralls.io/github/craigp/elixir-gmail?branch=master) [![hex.pm version](https://img.shields.io/hexpm/v/gmail.svg)](https://hex.pm/packages/gmail) [![hex.pm downloads](https://img.shields.io/hexpm/dt/gmail.svg)](https://hex.pm/packages/gmail)
============

A simple Gmail REST API client for Elixir, mostly built as a learning exercise.

You can find the hex package [here](https://hex.pm/packages/gmail), and the docs [here](http://hexdocs.pm/gmail).

You can find documentation for Gmail's API at https://developers.google.com/gmail/api/

## Usage

First, add the client to your `mix.exs` dependencies:

```elixir
def deps do
  [{:gmail, "~> 0.0.17"}]
end
```

Then run `$ mix do deps.get, compile` to download and compile your dependencies.

Finally, add the `:gmail` application as your list of applications in `mix.exs`:

```elixir
def application do
  [applications: [:logger, :gmail]]
end
```

## Notes

#### API Support

Client support is planned for:

* [x] Threads
* [x] Messages
* [x] Labels
* [ ] Drafts
* [ ] History
* [ ] Attachments

#### Auth

As of now the library doesn't do the initial auth generation for you; you'll
need to create an app on the [Google Developer
Console](https://console.developers.google.com/) to get a client ID and secret
and authorize a user to get an authorization code, which you can trade for an
access token. 

The library will however, when you supply a refresh token, use that to refresh
an expired access token for you. Take a look in the `dev.exs.sample` config
file to see what your config should look like.

### TODO
* [x] Stop mocking HTTP requests and use [Bypass](https://github.com/PSPDFKit-labs/bypass) instead
* [x] Add format option when fetching threads
* [ ] .. and messages
* [ ] .. and drafts
* [ ] Batched requests

