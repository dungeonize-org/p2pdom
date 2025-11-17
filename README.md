# p2pdom --- Universal Document Object Gateway for Peer-to-Peer Networks

## Overview

**p2pdom** is a Dungeonize project that transforms data from **any
peer-to-peer system** --- BitTorrent, IPFS, Ethereum, libp2p, Kademlia
DHT, and more --- into a unified **Document Object** that can be viewed
and explored in a web browser.

P2P networks expose hashes, blocks, peers, and binary objects.\
p2pdom adds a human-readable abstraction layer:

**P2P Data → Gateway → Document Object (HTML/JSON) → Exploratory Web
UI**

This allows decentralized data to be understood, explored, and embedded
like a document.

------------------------------------------------------------------------

## Supported (Pluggable) Backends

p2pdom converts heterogeneous P2P systems into a single unified document
model. Planned providers include:

-   **BitTorrent** --- torrent metadata, file trees, swarm information\
-   **IPFS** --- DAG nodes, CIDs, CAR files\
-   **Ethereum / EVM chains** --- blocks, transactions, logs\
-   **libp2p nodes** --- gossip messages, streams, peer info\
-   **Kademlia / DHT** --- key/value stores, peer tables\
-   **Custom P2P networks** --- via a plugin interface

Each backend implements the **Document Provider Interface** and outputs
a standard Document Object.

------------------------------------------------------------------------

## Document Object Format (Draft)

All P2P inputs are normalized into the following structure:

``` json
{
  "type": "ipfs | torrent | eth | dht | ...",
  "id": "string",
  "meta": {},
  "structure": [],
  "content": "",
  "preview": "",
  "links": []
}
```

This Document Object can be returned as:

-   HTML (human view)\
-   JSON (API / automation)\
-   Embeddable widget in other applications

------------------------------------------------------------------------

## Gateway Features

### 1. Document Object Generation

Converts torrent metadata, IPFS DAGs, Ethereum blocks, or DHT items into
structured documents.

### 2. Gateway Fetcher

The gateway connects to P2P networks on behalf of users:

-   Fetches metadata\
-   Streams content\
-   Offers HTTP/JSON/WebSocket APIs\
-   Requires **no P2P capabilities in the browser**\
-   Optional caching for performance

### 3. Dungeonize Philosophy

p2pdom follows the Dungeonize mission:

**"To Dungeonize Everything --- turning data into explorable worlds."**

P2P structures become rooms, corridors, artifacts, and portals.\
A hash becomes a doorway.\
A CID becomes a chamber.\
A block becomes a room.\
The network becomes a dungeon.

------------------------------------------------------------------------

## API (Draft)

### Create Document Object

    POST /api/create
    {
      "type": "torrent | ipfs | eth | dht",
      "value": "<magnet | CID | blockHash | key>"
    }

### Get Document Object (HTML)

    GET /doc/<id>

### Get Document Object (JSON)

    GET /doc/<id>.json

### Stream / Fetch Content

    GET /stream/<id>/<path>

------------------------------------------------------------------------

## Roadmap

-   [ ] Unified Document Object schema\
-   [ ] Torrent provider\
-   [ ] IPFS provider\
-   [ ] Ethereum provider\
-   [ ] DHT provider\
-   [ ] Caching and acceleration layer\
-   [ ] Dungeon-style visualization UI\
-   [ ] Integration with Dungeonize Search

------------------------------------------------------------------------

