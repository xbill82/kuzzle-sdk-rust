<p align="center">
  <img src="https://user-images.githubusercontent.com/7868838/52912711-4c2d0900-32b5-11e9-9064-472b025c886e.png"/>
</p>
<p align="center">
  <img src="https://img.shields.io/badge/tested%20on-linux%20%7C%20osx-blue.svg">
  <a href="https://github.com/alexandrebouthinon/kuzzle_sdk/blob/master/LICENSE">
    <img alt="undefined" src="https://img.shields.io/github/license/alexandrebouthinon/kuzzle_sdk.svg?style=flat">
  </a>
  <a href="https://travis-ci.com/alexandrebouthinon/kuzzle_sdk">
    <img src="https://travis-ci.com/alexandrebouthinon/kuzzle_sdk.svg?branch=1-dev"/>
  </a>
  <a href="https://codecov.io/gh/alexandrebouthinon/kuzzle_sdk">
    <img src="https://codecov.io/gh/alexandrebouthinon/kuzzle_sdk/branch/1-dev/graph/badge.svg" />
  </a>
</p>


## About 

<p align="center">
  <em> :warning: Work in progress. Do not use in production. :warning: </em>
</p>

### Rust SDK

This is the community supported Rust SDK for the free and open-source backend Kuzzle.
Goal is to provide the Rust community with a production-ready Kuzzle SDK using only the Rust stable toolchain.

### Kuzzle

Kuzzle is an open-source backend that includes a scalable server, a multiprotocol API,
an administration console and a set of plugins that provide advanced functionalities like real-time pub/sub, blazing fast search and geofencing.

* :octocat: __[Github](https://github.com/kuzzleio/kuzzle)__
* :earth_africa: __[Website](https://kuzzle.io)__
* :books: __[Documentation](https://docs-v2.kuzzle.io)__
* :email: __[Gitter](https://gitter.im/kuzzleio/kuzzle)__

## Usage

### Declaration

Add this to your `Cargo.toml`:

```toml
[dependencies]
kuzzle_sdk = "^0.1"
```
and this to your crate root:

```rust
extern crate kuzzle_sdk;
```
### Example

```rust
extern crate kuzzle_sdk;
use kuzzle_sdk::kuzzle::Kuzzle;
use kuzzle_sdk::protocols::Http;
use kuzzle_sdk::types::KuzzleOptions;
             
fn main() {
  // Instanciate your Kuzzle client                                    
  let kuzzle = Kuzzle::new(
      Http::new(
          KuzzleOptions::new("localhost", 7512)
      )
  );
                                                   
  // Access Kuzzle's features via its controllers 
  match kuzzle.server().now() {
      // This will display the current timestamp in Epoch millisecond format
      Ok(timestamp) => println!("{}", timestamp),
      Err(error) => eprintln!("{}", error);
  }
}
```

## Development activity

<p align="center">
    <b>Any help is welcome, take a look at the <a href="https://github.com/alexandrebouthinon/kuzzle_sdk/blob/1-dev/CONTRIBUTING.md">CONTRIBUTING.md</a> file :wink:</b>
</p>

<p align="center">
  <a href="https://waffle.io/alexandrebouthinon/kuzzle_sdk/metrics/throughput">
    <img src="https://graphs.waffle.io/alexandrebouthinon/kuzzle_sdk/throughput.svg" alt="Throughput Graph">
  </a>
</p>







