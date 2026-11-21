# arknetz-actions

Shared, vetted GitHub Actions workflows used by all central ArkNetzWebWeaver
repos (MIT). Update once, roll out everywhere; no copy-paste workflow drift
between the 16 registry shards.

- `.github/workflows/register.yml` — domain-claim flow (REGISTER Issue →
  availability/banned-word checks → commit `registry.json` +
  `registry.json.zst` → close the issue). One copy also lives in each
  registry shard repo, so one shard's queue never blocks another's.
  Source: `protocol/register.yml` in the client repo.
- `.github/workflows/cleanup.yml` — monthly history squash
  (PROTOCOL.md §5), on a monthly schedule plus manual dispatch.
- `.github/workflows/stats.yml` — nightly VIEW_PING rollup for site repos
  (PROTOCOL.md §3.10), writing the app's real SiteStats shape.
