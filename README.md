# evidentia-anchors-dev — development anchors, not evidence

This repository is a **development** witness. The roots published here describe
throwaway databases that get reset routinely. Nothing in it should be relied on
as evidence of anything. The production anchors repository is separate.

## What is in here

One file per UTC day under `roots/`, named `roots/YYYY-MM-DD.txt`, holding the
64 hexadecimal characters of that day's Merkle root and a trailing newline.
Files are only ever added; none is ever modified.

Each root is the root of a Merkle tree whose leaves are the per-tenant hash
chain heads at the end of that day, padded to a fixed width so that the number
of leaves discloses neither how many tenants exist nor which were active.
Nothing here identifies a customer, counts them, or reveals their volume.

## What a root proves

A root committed on a given date shows that the chain heads it covers existed
in that form on that date, and nothing earlier — a root published late proves
only what was asserted when it was published.

It proves nothing about completeness: a request that was never captured leaves
no gap in any chain.
