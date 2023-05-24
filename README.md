# ethereum-node-list

The Ethereum node list is a community-led initiative to improve discoverability of RPC gateways in a manner that is inclusive and transparent.

## A new Ethereum node list standard

As the Ethereum ecosystem continues to evolve, we continue to see growth in the number of RPC gateways. This maturation reflects the success of permissionless innovation.

While most dapps rely on a browser-based wallet provider to connect them to the Ethereum blockchain, not every dapp has this luxury. Desktop and mobile dapps, for example, need to decide what RPC endpoint to connect to. Hardcoding this piece of information is undesirable. RPC gateways can disappear or be offline at any given moment. Such dapps will want to enumerate over all available RPC gateways, allow the user to select a few preferred gateways, and select the one with the lowest latency.

This repo contains the Ethereum node list, and client implementations for working with the node list.

Desktop and mobile dapps can pull the raw list [here](https://raw.githubusercontent.com/svanas/ethereum-node-list/main/ethereum-node-list.json). Users of such dapps can select preferred gateways as initial discovery. In case of failure and based on priority, the dapp should select the gateway from the list with the lowest latency.

We hope to continue iterating and improving the Ethereum node list in collaboration with the broader community. If a new RPC gateway is released by a reputable team, the community can [open a PR](https://github.com/svanas/ethereum-node-list/pulls) and update the list. Any dapp subscribed to the list can automatically import it in real time.

## Versioning

The list includes a `version` field, which follows [semantic versioning](https://semver.org).

List versions must follow the rules:

* Increment major version when a node is removed
* Increment minor version when a node is added
* Increment patch version when a node already on the list has minor details changed

Changing a chain ID or an andpoint is considered both a remove and an add, and should be a major version update.

Note that list versioning is used to improve the user experience, but not for security, i.e. list versions are not meant to provide protection against malicious updates to the node list; i.e. the list semver is used as a lossy compression of the diff of list updates. List updates may still be diffed in the dapp.

## Other sources

A big thanks to these other options for existing. They each paved the way to make Ethereum nodes discoverable.

* David Mihal's [ethereumnodes.com](https://ethereumnodes.com/)
* Ardian Luma's [awesome-list-rpc-nodes-providers](https://github.com/arddluma/awesome-list-rpc-nodes-providers)
* DeFi Llama's [chainlist](https://chainlist.org/)
* Alchemy's [Chain Connect](https://www.alchemy.com/chain-connect)

## Acknowledgement

Special thanks to [Juan Blanco](https://github.com/juanfranblanco) for his help on this initiative.

## Disclaimer

The Ethereum node list is provided free to charge. There is no warranty and no independent audit has been or will be commissioned. You are encouraged to read the list and decide for yourself whether it is secure. The authors do not assume any responsibility for bugs, vulnerabilities, or any other technical defects.
