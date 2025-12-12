# 39937

The problem: `pyproject.toml` contains both `django-types==0.22.0` and a `tool.uv.sources.django-types` table containing an exact git version.

## Current behavior

There is a warning in the Renovate Dependency Dashboard:

> [!WARNING]
> Renovate failed to look up the following dependencies: `Could not determine new digest for update (git-refs package https://github.com/sbdchd/django-types)`.
>
> Files affected: `pyproject.toml`

## Expected behavior

One of the following:

- There shouldn't be a warning, and Renovate should update from 0.22.0 to 0.23.0 (and remove the git pin) whenever 0.23.0 is released
- There should be a warning explicitly stating that there are conflicting requirements, suggesting to remove either the `==0.22.0` or the git pin

## Link to the Renovate issue or Discussion

https://github.com/renovatebot/renovate/discussions/39937
