# The update feed

`releases.json` on this branch is what every installed FediPilot reads to decide
whether a newer version exists. The Cloudflare Worker in the private source
repository serves it verbatim.

**Do not edit it by hand.** It is written by the `publish-feed` workflow when a
release is published, and that workflow validates things a human editing JSON
will not: that `version` is the build's commit sha rather than the product
version, that every required field is present, and that each `url` really
returns 200. A malformed entry does not produce an error anywhere -- the client
silently drops the update and looks idle -- so those checks are the only thing
standing between a typo and a fleet that quietly stops updating.

## Why this is not on `main`

Two reasons, and the second is the real one.

The organisation protects default branches: `main` requires a pull request, and
GitHub Actions cannot bypass that (only repository admins can). This branch is
not the default, so the workflow can write to it without anyone weakening that
policy.

More importantly, the file that decides what every installed copy downloads
should not sit on the branch people casually edit. Keeping it here means a
change to it is deliberate.
