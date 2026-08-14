# comet-contracts-archive

Cached verified-source build files for contracts used by [comet](https://github.com/woof-software/comet), so `spider` doesn't have to re-fetch them from Etherscan/Blockscout/Sourcify on every run.

## Layout

```
{network}/.contracts/{address}.json
```

Each file is a `BuildFile` — same shape `comet`'s own local cache uses, copied over as-is.

## How entries get here

- **Manual**: copied over from a dev's local `deployments/{network}/.contracts/`.
- **Automatic**: written back by `comet` CI whenever it has to fetch something live that isn't archived yet.

Either way, an entry is just a cached copy of what an explorer already returned for that address.

## Consuming

comet uses this in as a git submodule and merges it into its local cache before spidering.
