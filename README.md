# Pithyx community apps

This repository is the **community app catalog of [Pithyx](https://github.com/pithyx)**: apps by developers outside the project, reviewed by the Pithyx project before they are published, in the Store's tab "Community". It is **enabled by default on a box**; an administrator can turn it off in the Store's settings. Ids under `org.pithyx.*` are not allowed here.

Part of Pithyx by Schecher1 (https://github.com/Schecher1).

## Structure

- `master`: the source of every app in `apps/<id>/` (it starts empty), changed only by reviewed pull requests, and `catalog.json`.
- `catalog-next`: written by CI after each merge, signed with the `next` key; boxes on the beta channel read it.
- `catalog`: written by the `promote` workflow after the owner's approval, signed with the `catalog` key; boxes on the stable channel read it.
- Images: `ghcr.io/pithyx/community/<id>/<service>:<version>`, linked only by digest.
- `vendor/`: temporary copy of `@pithyx/cli` 1.0.0-rc.5, which the workflows install until it is on npm; it goes once the owner publishes that version.

To submit an app, read [CONTRIBUTING.md](CONTRIBUTING.md). How a catalog works and what its CI does is explained in the [catalog template](https://github.com/pithyx/catalog-template); security reports go through [SECURITY.md](SECURITY.md).
