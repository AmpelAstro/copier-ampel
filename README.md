# copier template for Ampel plug-ins

A [copier](https://copier.readthedocs.io) template that covers the boring bits of a new Ampel plugin, including:
- Skeleton directories for tests, config, plugin code, etc
- Project setup and core dependencies
- Pre-commit linting with ruff
- CI/CD
- Renovate setup

## Quickstart

1. [Install copier](https://copier.readthedocs.io/en/stable/#installation)
2. Generate a new project skeleton: `copier copy https://github.com/AmpelAstro/copier-ampel.git /path/to/new/project`
3. Add code, tests, push to a new repo

## Updating the template

Avoid changing content rendered by the template in your downstream project (.github, pyproject.toml, .pre-commit-config.yaml, renovate.json, etc). Instead, make a PR against this template repo, and once it is merged and a new release made, update your downstream repo with `copier update`. This way, all templated projects can benefit from updates.

## Publishing to PyPI

The rendered template includes a CD stage that uses PyPI's Trusted Publisher workflow to publish packages. If you want your package to go to PyPI (a requirement for inclusion in e.g. the Ampel instance listening to the LSST alert stream), you need to do the following:

1. Transfer your repository to the AmpelAstro organization
2. Ask an Ampel maintainer to create a [pending publisher](https://docs.pypi.org/trusted-publishers/creating-a-project-through-oidc/) for the package.
3. Tag a release (either explicitly, or by incrementing the project version in pyproject.toml). When CI passes, a new release will be pushed to PyPI.

You may also keep the repo under your ownership and create a pending publisher yourself, but then also keep responsibility for maintenance.
