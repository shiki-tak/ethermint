[![CircleCI](https://circleci.com/gh/cosmos/ethermint.svg?style=svg)](https://circleci.com/gh/cosmos/ethermint)
[![](https://godoc.org/github.com/cosmos/ethermint?status.svg)](http://godoc.org/github.com/cosmos/ethermint) [![Go Report Card](https://goreportcard.com/badge/github.com/cosmos/ethermint)](https://goreportcard.com/report/github.com/cosmos/ethermint)

# Ewasmint(Ethermint powered by eWASM)

- Check the [docs](./docs/README.md) for the original README.

### The projects I referred to in order to use ewasm.

- evmc: API to connect to the Ethereum client
  - https://github.com/ethereum/evmc ...
- ssvm-evmc: WebAssembly VM for EVMC
  - https://github.com/second-state/ssvm-evmc
- SSVM: WebAssembly Virtual Machine, not necessarily a blockchain It's not a VM for
  - https://github.com/second-state/SSVM

### Building Ewasmint

To build, execute the following commands:

```bash
# To prepare go-ethereum, evmc for ewasm vm
make prepare

# Build ewasm library
# get <your/build/folder>/tools/ssvm-evmc/libssvm-evmc.dylib on Mac
git clone https://github.com/second-state/ssvm-evmc.git
cd ssvm-evmc
mkdir -p build && cd build
cmake -DCMAKE_BUILD_TYPE=Release -DBUILD_TESTS=ON .. && make

# To build the project and install it in $GOBIN
make install

# To build the binary and put the resulting binary in ./build
make build
```