# garnet-guard-action-test

A throwaway repository for testing the [Garnet Guard](https://github.com/orca-solutions/garnet-guard) GitHub Action on real dependency update pull requests: one from Renovate and one from a fork.

The project pins slightly old versions on purpose, so Renovate opens update pull requests right away:

- `pyproject.toml` and `uv.lock` pin `requests` 2.32.3 (Renovate's `pep621` manager).
- `requirements.txt` pins `pluggy` 1.6.0 (Renovate's `pip_requirements` manager). Garnet Guard warns on pluggy 1.7.0, because it was published from a different workflow (GRN-T003), so this pull request should get a real finding.

`.github/workflows/garnet-guard.yml` is the single-workflow example from `action/examples/garnet-guard.yml`, with SARIF turned on and the Action pinned to the v0.1.0a1 commit.

Nothing here is installed or deployed. Delete the repository once the test is written up.
