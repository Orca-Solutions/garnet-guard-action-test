# garnet-guard-action-test

A throwaway repository for testing the [Garnet Guard](https://github.com/orca-solutions/garnet-guard) GitHub Action on real dependency update pull requests: one from Renovate and one from a fork.

The project pins slightly old versions on purpose, so Renovate opens update pull requests right away:

- `pyproject.toml` and `uv.lock` pin `requests` 2.32.3 (Renovate's `pep621` manager).
- `requirements.txt` pins `pluggy` 1.6.0 (Renovate's `pip_requirements` manager). Garnet Guard warns on pluggy 1.7.0, because it was published from a different workflow (GRN-T003), so this pull request should get a real finding.

The workflows are the two-workflow fork pattern from `action/examples/`: `garnet-guard.yml` is `garnet-guard-fork.yml` (check with a read-only token, upload the report) and `garnet-guard-comment.yml` posts the comment from a `workflow_run`. Both pin the Action to the v0.1.0a1 commit. The first round of the test used the single-workflow example with SARIF on.

Nothing here is installed or deployed. Delete the repository once the test is written up.
