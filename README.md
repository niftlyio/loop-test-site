# Loop test site

A throwaway Astro website for a made-up bakery. Niftly uses it as the target when testing the AI update loops in the client portal, so real client sites are never used for tests.

Nothing here is real: the business, phone number and address are placeholders.

## Run it

    pnpm install
    pnpm dev

`pnpm check` type-checks the site and `pnpm build` builds it into `dist/`.

## How the loop reaches this repo

1. A test client requests an update in the Niftly portal.
2. An admin approves the drafted task. The portal opens an issue here and adds the `agent-ready` label.
3. `.github/workflows/loop-agent.yml` runs Claude Code on the issue, which opens a pull request that says `Fixes #<issue>`.
4. The portal picks up the pull request and marks the task ready for review.

## One-time setup

- Install the Niftly loops GitHub App on this repository.
- Install the Claude GitHub App on this repository.
- Add an `ANTHROPIC_API_KEY` Actions secret.

Pull requests opened by test runs can be closed without merging.
