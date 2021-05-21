# Use `asdf` For Dyno-related Dependency Management

When working on several development projects, language versioning can be an issue when one project
has dependencies that prevent upgrading the language version. For MacOS users, typically this means
using `homebrew` and linking/unlinking kegs.

While looking for the best way to manage language versions for local development, I found the `asdf`
utility which has support for all the languages the Digital Engagement team currently uses. It
claims to make the process way easier, and I have been using it.

## Sponsors

- Alex Finnarn - DE Front-end Developer - alexander.finnarn@cu.edu

## Status

- **Proposed** - Using `asdf` is only proposed at this point in time. Developers use different
  methods for local development and language versioning.

## Prior Art

The internet led me to `asdf`, but I'll list the main docs site and a blog post:

- `asdf` docs site: https://asdf-vm.com/#/core-manage-asdf
- blog post about `asdf` vs. other version managers: 
  https://dev.to/0xdonut/manage-your-runtime-environments-using-asdf-and-not-nvm-or-rvm-etc-2c7c

## Current Context

The genesis of this ADR proposal came from a Heroku deployment log. It said to upgrade the version
of Ruby being used in an app, and that began a search on using `rvm` a version manager for the Ruby
language.

Naturally, `asdf` also showed up in the search results since people were using a version manager per
language instead of one versioning tool that worked across languages. That concept made a lot of
sense and hence an ADR was born.

Docker containers are also an option for version management, but MacOS file syncing previously had
an issue that caused noticable slowdowns while developing locally. Docker can still be used for
Heroku add-on services, but until the file syncing issues are resolved, I think using `asdf` is a
more productive solution.

## Decision

We should use `asdf` for language version management locally.

## Consequences

An alternative solution to language versioning could be to use 
[Docker and the Heroku Container Registry](https://devcenter.heroku.com/articles/container-registry-and-runtime)
.

You can use one of their "stacks" to mimic the Heroku dyno environment on production, but there
would be more time needed to assess supporting doing local development and production deploys using
this method.

Based on this decision, DE documentation has been updated
at: https://github.com/CUCentralAdvancement/heroku-docs#language-version-manager

Ideally, all project repositories will have documentation on language version management within the
repository. 
