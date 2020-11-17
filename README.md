# Pirl

Implementation of a https://pirl.io node in Rust based on the Substrate framework.


[Pirl Docs](https://docs.pirl.io).

## Installation

If you just wish to run a Pirl node without compiling it yourself, you may
either run the latest binary from our
[releases](https://github.com/pirl/pirl2/releases) page, or install
Pirl from one of our package repositories.

### Connect to Pirl Mainnet

Connect to the global Polkadot Mainnet network by running:

```bash
./target/release/pirl --chain=pirl
```

You can see your node on [telemetry] (set a custom name with `--name "my custom name"`).

[telemetry]: https://telemetry.polkadot.io/#list/Pirl

pirl --port 30333   --ws-port 9944   --rpc-port 9933         --unsafe-rpc-external      --unsafe-ws-external   --ws-external    --rpc-methods=unsafe  --rpc-external --rpc-cors all --validator --telemetry-url 'wss://telemetry.polkadot.io/submit/ 0'  --alice
