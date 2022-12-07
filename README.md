# okp4
Want to become a validator?
Validators are responsible for securing the okp4 network. Validator responsibilities include maintaining a functional node with constant uptime and providing a sufficient amount of $KNOW as stake. In exchange for this service, validators receive block rewards and transaction fees.

Want to become a validator? 👉 Checkout the documentation!

Looking for a network to join ? 👉 Checkout the networks!

Supported platforms
The okp4d blockchain currently supports the following builds:

Platform	Arch	Status
Darwin	amd64	✅
Darwin	arm64	✅
Linux	amd64	✅
Linux	arm64	✅
Windows	amd64	️🚫
Not supported
Note: as the blockchain depends on CosmWasm/wasmvm, we only support the targets supported by this project.

Releases
All releases can be found here.

okp4d follows the Semantic Versioning 2.0.0 to determine when and how the version changes, and we also apply the philosophical principles of release early - release often.

Docker image
For a quick start, a docker image is officially available on Docker hub.

docker pull okp4/okp4d:latest
Get the documentation
docker run okp4/okp4d:latest --help
Query a running network
Example:

API_URL=https://api.devnet.okp4.network:443/rpc
WALLET=okp41pmkq300lrngpkeprygfrtag0xpgp9z92c7eskm

docker run okp4/okp4d:latest query bank balances $WALLET --chain-id okp4-devnet-1 --node $API_URL
Create a wallet
docker run -v $(pwd)/home:/home okp4/okp4d:latest keys add my-wallet --keyring-backend test --home /home 
Start a node
Everything you need to start a node and more is explained here: https://docs.okp4.network/docs/nodes/run-node

MONIKER=node-in-my-name
CHAIN_ID=localnet-okp4-1

docker run -v $(pwd)/home:/home okp4/okp4d:latest init $MONIKER --chain-id $CHAIN_ID --home /home 
This will create a home folder, you can then update the config/genesis.json with one of this ones : https://github.com/okp4/okp4d/tree/main/chains/

Join a running network
Set persistent_peers in config/config.toml file.

Then start the node
docker run -v $(pwd)/home:/home okp4/okp4d:latest start --home /home
Developing & contributing
okp4d is written in Go and built using Cosmos SDK. A number of smart contracts are also deployed on the OKP4 blockchain and hosted in the okp4/contracts project.

Prerequisites
install Go 1.19+ following instructions from the official Go documentation;
use gofumpt as formatter. You can integrate it in your favorite IDE following these instructions or invoke the makefile make format-go;
verify that Docker is properly installed and if not, follow the instructions for your environment;
verify that make is properly installed if you intend to use the provided Makefile.
Makefile
The project comes with a convenient Makefile that helps you to build, install, lint and test the project.

$ make help

Usage:
  make <target>

Targets:
  Lint:
    lint                Lint all available linters
    lint-go             Lint go source code
    lint-proto          Lint proto files
  Format:
    format              Run all available formatters
    format-go           Format go files
  Build:
    build               Build all available artefacts (executable, docker image, etc.)
    build-go            Build node executable for the current environment (default build)
    build-go-all        Build node executables for all available environments
  Install:
    install             Install node executable
  Test:
    test                Pass all the tests
    test-go             Pass the test for the go source code
  Clean:
    clean               Remove all the files from the target folder
  Proto:
    proto-format        Format Protobuf files
    proto-build         Build all Protobuf files
    proto-gen           Generate all the code from the Protobuf files
  Documentation:
    doc-proto           Generate the documentation from the Protobuf files
    doc-command         Generate markdown documentation for the command
  Release:
    release-assets      Generate release assets
  Help:
    help                Show this help.

This Makefile depends on docker. To install it, please follow the instructions:
- for macOS: https://docs.docker.com/docker-for-mac/install/
- for Windows: https://docs.docker.com/docker-for-windows/install/
- for Linux: https://docs.docker.com/engine/install/
Build
To build the okp4d node, invoke the goal build of the Makefile:

make build
The binary will be generated under the folder target/dist.

Bug reports & feature requests
If you notice anything not behaving how you expected, if you would like to make a suggestion or would like to request a new feature, please open a new issue. We appreciate any help you're willing to give!

Don't hesitate to ask if you are having trouble setting up your project repository, creating your first branch or configuring your development environment. Mentors and maintainers are here to help!

Community
The OKP4 Discord Server is our primary chat channel for the open-source community, software developers and node operators.

Please reach out to us and say hi 👋, we're happy to help there.
