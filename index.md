---
layout: default
---

# `NO_COLOR`
### Last updated: {{ 'now' | date: "%Y-%m-%d" }}

An increasing number of command-line software programs output text with
[ANSI color](https://en.wikipedia.org/wiki/ANSI_escape_code#Colors)
escape codes by default.
While some developers and users obviously prefer seeing these colors,
many users don't.
Unfortunately, every new piece of software seems to have a different way
of disabling colored text output and some software has no way at all.

Accepting the futility of trying to reverse this trend, an informal standard
is hereby proposed:

> **All command-line software which outputs text with ANSI color added should
check for the presence of a `NO_COLOR` environment variable that, when present
(regardless of  its value), prevents the addition of ANSI color.**

By adopting this standard, users that prefer to have plain, non-colored text
output can just set one environment variable in their shell to have it affect
all supported software.

This website will attempt to document which software has adopted this standard
and when.
For software that has not or will not adopt this standard, an attempt will be
made to document how to otherwise disable color.

To add software to this site,
[clone this site's Git repository](https://github.com/jcs/no_color)
and submit a pull request.

## Software supporting `NO_COLOR`

| Software | Version/Date Supported |
|:-|:-|
| [Snow](https://github.com/mortie/snow) | Supported from 2018-01-24 |
{: rules="groups"}

## Disabling color in software not supporting `NO_COLOR`

| Software | Method |
|:-|:-|
| [Bundler](https://bundler.io/) | `bundle COMMAND --no-color` ([Docs](https://bundler.io/v1.15/man/bundle.1.html)) |
| [Clang](https://clang.llvm.org/) | `-fno-color-diagnostics` ([Docs](https://clang.llvm.org/docs/UsersManual.html#formatting-of-diagnostics)) |
| [Cocoapods](https://cocoapods.org/) | `pod COMMAND --no-ansi` ([Docs](https://guides.cocoapods.org/terminal/commands.html#pod_install)) |
{: rules="groups"}

## Software with no mechanism to disable color

| Software | Notes |
|:-|:-|
| [Homebrew](https://brew.sh/) | [Rejected `NO_COLOR` patch](https://github.com/Homebrew/brew/pull/3090) |
{: rules="groups"}
