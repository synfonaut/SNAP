# Semantic Nonce Attribute Protocol (SNAP)

![Semantic Nonce Attribute Protocol (SNAP)](https://media.giphy.com/media/13sJFV64YRIc1y/giphy.gif)

`Generate proof-of-work hashes with semantic meaning`

SNAPS are magic data structures, semantic data with a nonce that is used to generate 21e8 proof-of-work hashes.

This protocol offers a flexible data structure for ingesting semantic data into a 21e8 proof-of-work hash. It's based on the [Magic Attribute Protocol](https://github.com/rohenaz/MAP/tree/v2) and [Bitcoin Schema](https://github.com/synfonaut/MAP/blob/v2/README.md#map-schema).

1. SNAP Bitcoin Schema `(b843b7c73549a6e24b073777b936051f314804e43ef4a243f49407cc562ac9dd)`
   1. nonce (Integer)
   2. Optional: parent (Hash)
   3. Optional: namespace (String)
   4. Extension: tags (List)

## Bitcoin Schema

SNAP is based on [Bitcoin Schema](https://github.com/synfonaut/MAP/blob/v2/README.md#map-schema) and the [Magic Attribute Protocol](https://github.com/rohenaz/MAP/tree/v2) (MAP). MAP allows flexible key/value data in Bitcoin protocols. Bitcoin Schema allows semantic layers on top.

## Bitcoin Schema

Bitcoin Schema defines a set of key/values for a specific context, identified by a txid.

```json
MAP SCHEMA <SNAP>
```

### Parent

Parent refers to a 21e8 parent hash derived from a world key. If there is no parent, this hash becomes a world key.

```json
MAP SCHEMA <SNAP> | MAP
SET
parent
21e80096c21e2de52d741ac27607e251770c0b9f7e644f684cf37173e871820e
```

### Namespace

Namespaces are valuable for specific derivation paths or generating UUIDs to avoid hash collisions.

```json
MAP SCHEMA <SNAP> | MAP
SET
namespace
universe-green-apple
```

### Nonce

Nonce is an integer that gets flipped to generate the 21e8 hash with appropriate proof-of-work.

```json
MAP SCHEMA <SNAP> | MAP
SET
nonce
1221348
```

## SELECT

Using MAP SELECT can associate data on other hashes

```json
MAP SCHEMA <SNAP> |
MAP SELECT <txid|21e8>
ADD
tags
bitcoin
bsv
```

## Extension: tags

Add tags to a proof of work hash.

```json
MAP SCHEMA <SNAP> | MAP
ADD
tags
bsv
bitcoinsv
bitcoin
```

# Full Example

```json
MAP SCHEMA <SNAP> | MAP
SET
parent
21e80b8c4faf426f31db9bc7c03359a6e79b3faabc015b45af748dbae4353323
namespace
123-123-123-1234
nonce
1070434
ADD
tags
bsv
bitcoinsv
bitcoin
```

## Contact

@synfonaut

## Ideas
* Hierarchy PoW more explicit
* IP transfer
