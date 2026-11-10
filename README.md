# Rapid Networks `.github`

Default community files, templates and shared CI config for every repo in the
Rapid Networks organisation.

> [!IMPORTANT]
> This repo is public, and changes take effect across the organisation as soon
> as they're merged. Never add secrets, internal hostnames or customer data.

## What's in here

| Path | Purpose |
|---|---|
| [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md), [`CONTRIBUTING.md`](CONTRIBUTING.md), [`SECURITY.md`](SECURITY.md), [`SUPPORT.md`](SUPPORT.md) | Default policies shown in every repo |
| [`.github/ISSUE_TEMPLATE/`](.github/ISSUE_TEMPLATE/) | Default bug and feature forms, and issue contact links |
| [`.github/PULL_REQUEST_TEMPLATE.md`](.github/PULL_REQUEST_TEMPLATE.md) | Default PR template |
| [`profile/README.md`](profile/README.md) | The public organisation profile at github.com/Rapid-Networks |
| [`workflow-templates/`](workflow-templates/) | Starter workflows offered under **Actions → New workflow** |
| [`configs/`](configs/) | Shared tool config for repos to copy (e.g. golangci-lint) |
| [`LICENSE`](LICENSE) | Licence for this repo only |

## How defaults work

GitHub uses the files here for any org repo that doesn't have its own version.

- A repo's own file always wins. For example, a `SECURITY.md` in a repo replaces
  the one here for that repo.
- Issue templates are all-or-nothing. If a repo has **any** files in its own
  `.github/ISSUE_TEMPLATE/` folder, none of the defaults apply there.
- `LICENSE` isn't inherited. Each repo needs its own.
- Default issue templates add the `bug` and `enhancement` labels, so those labels
  need to exist in each repo. GitHub creates them by default.

## Setting up a Go repo

1. In the repo, go to **Actions → New workflow** and choose
   **Rapid Networks Go CI**.
2. Copy [`configs/golangci.yml`](configs/golangci.yml) to the repo root as
   `.golangci.yml`. golangci-lint can't load a remote config, so each repo keeps
   its own copy. Add repo-specific exceptions at the end of `exclusions.rules`.

## Making changes

- Open a PR. Changes here affect every repo, so get a review first.
- When you update `configs/golangci.yml`, let repo owners know so they can update
  their copies.
- Where possible, we prefer UK spelling in prose (colour, behaviour,
  organisation).
