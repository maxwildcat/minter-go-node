# minter-go-node

Running a Minter blockchain node lets you participate in a network for custom coins, rewards, and loyalty points. minter-go-node provides the Go node implementation, based on MinterTeam/minter-go-node.

## Features

- Run a node on the Minter blockchain with the `minter node` command.
- Support a network where brands and communities can create their own coins for rewards and loyalty systems.
- Build the node from Go source or run it through the repository's Docker Compose configuration.

## Installation

Install Go and Git, then clone this project's repository and open its directory. Run these commands from the repository root:

```bash
go mod download
go build -o ./minter ./cmd/minter
```

The donor README lists Go 1.15. Check this checkout's `go.mod` for its declared Go version before building.

If you prefer Docker and the checkout includes `docker-compose.yml`, build and start the service with:

```bash
docker-compose up --build -d
```

For production deployments, the donor recommends a bind mount on the host rather than a Docker-managed volume for node data.

## Usage

Start the node with the binary built above:

```bash
./minter node
```

The executable is named `minter`, even though the project is named minter-go-node. The `node` subcommand starts the node process.

See the [Minter documentation](https://docs.minter.network) for network configuration and operational instructions. These are upstream resources; check their instructions against the version in this checkout.

**Production caution:** the donor README labels the software as alpha. Review configuration, data persistence, and upgrade compatibility before using it with funds or production workloads.

## License

Licensed under the MIT License. This project is based on [MinterTeam/minter-go-node](https://github.com/MinterTeam/minter-go-node).

Retain the upstream copyright notice and MIT permission notice in copies or substantial portions of the software. See `LICENSE` for the full terms.
