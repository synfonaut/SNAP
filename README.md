# Semantic Nonce Attribute Protocol (SNAP)

`SNAPS are Magic Data Structures turned 21e8 pow checksums`

SNAP offers a flexible data structure for ingesting semantic data into a 21e8 proof-of-work hash. It's composed of:

1. Magic Attribute Protocol
2. Bitcoin Schema
   1. parent
   2. namespace
   3. nonce
4. Extension: tags
5. Extension: SELECT

## Magic Attribute Protocol

The Magic Attribute Protocol (MAP) allows flexible key/value data in Bitcoin protocols. SNAP is a MAP protocol with semantic layers (Bitcoin Schema) on top.

## Bitcoin Schema

Bitcoin Schema defines a set of key/values for a specific context.

### Parent

Parent refers to a 21e8 parent hash derived from a world key. If there is no parent, this hash becomes a world key.

```
MAP
SET
parent
21e80096c21e2de52d741ac27607e251770c0b9f7e644f684cf37173e871820e
```

### Namespace

Namespaces are valuable for derivation paths or generating UUIDs for avoiding hash collisions.

```
MAP
SET
namespace
universe-green-apple
```

### Nonce

Nonce is an integer that gets flipped to generate the 21e8 hash

```
MAP
SET
nonce
1221348
```



## Extension: tags

Add tags to a proof of work hash.

```
MAP
ADD
tags
bsv
bitcoinsv
bitcoin
```



## Extension: SELECT

Using MAP SELECT can associate data on other elements

```
MAP
SELECT <txid|21e8>
ADD
tags
bitcoin
bsv
```



# Full Example

```
MAP
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

* IP transfer
