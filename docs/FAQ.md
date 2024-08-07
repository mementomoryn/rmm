# ❓ Frequently Asked Questions

## 📜 Table of contents

* [What is this repository?](#what-is-this-repository)
* [What are the unique features of this fork?](#what-are-the-unique-features-of-this-fork)
* [Why there are no releases?](#why-there-are-no-releases-like-on-the-j-hc-repo)
* [What makes this one safe?](#revanced-surely-discouraged-pre-patched-apks-so-what-makes-this-one-safe)
* [How to make feature requests or contributions?](#how-to-make-feature-requests-or-contributes-to-the-repository)

## What is this repository?

This is a fork based on [j-hc/revanced-magisk-module repo](https://github.com/j-hc/revanced-magisk-module) with little twists & improvements of my own.

> [!NOTE]
> This is just a personal fork. I can't guarantee you stability, because i'm only working on this when i've the time.

## What are the unique features of this fork?

There isn't much, but these are some features that i like:

* Repository Syncing

Upstream: sync from `j-hc/revanced-magisk-module` [TODO]

Template: sync from `mementomoryn/rmm`

> [!TIP]
> If you want to, you can disable repo syncing directly from the workflow.
> * [`sync.yml`](../../../.github/workflows/sync.yml)
> * [`template_sync.yml`](../../../.github/workflows/template_sync.yml)

* Hide `client_id` token with **GitHub Secrets**
> [!CAUTION]
> Even though the `client_id` token is hidden on the repository. The token can still be found in generated APKs.

* Support replacing _signing keystore_ info

* Use custom `options.json` file per-app in `config.toml`

* **CalVer**, increment release version based on calendar.

* Automatically clear old workflow runs _weekly_.

* Options to only enable some apps in [`build.yml`](../../../.github/workflows/build.yml) workflow

## Why there are no releases like on the [j-hc repo](https://github.com/j-hc/revanced-magisk-module)?

It's kind of useless to continuously run CI workflow, when nobody will use the release APKs anyway. So unless there is other reasons, it'll probably stay that way.

Also this is a template repository, you can create your own repository with the [template maker](https://github.com/new?template_name=rmm&template_owner=mementomoryn).

## ReVanced surely discouraged pre-patched APKs, so what makes this one safe?

This repository is just a collection of _shell scripts_ to grab original APKs from internet source like **APKMirror**, **Uptodown**, and **Internet Archive**, then patch it with **Patches**, **Integrations**, and **CLI** of your choice in `config.toml` using **GitHub Workflow Actions**.

If you're still not fully convinced, feel free to use the official way [here](https://revanced.app/).

## How to make feature requests or contributes to the repository?

I don't accept feature requests and code contributions. If you wanted to, you can simply do it [upstream](https://github.com/j-hc/revanced-magisk-module).
