# ❓ Frequently Asked Questions

## 📜 Table of contents

* [What is this repository?](#what-is-this-repository)
* [What are the features of this fork?](#what-are-the-features-of-this-fork)
* [Why there are no releases?](#why-there-are-no-releases-like-on-the-j-hc-repo)
* [What makes this one safe?](#revanced-surely-discouraged-pre-patched-apks-so-what-makes-this-one-safe)
* [How to make feature requests or contributions?](#how-to-make-feature-requests-or-contributes-to-the-repository)

## What is this repository?

This is a fork based on [j-hc/revanced-magisk-module repo](https://github.com/j-hc/revanced-magisk-module) with little twists & improvements of my own.

> [!NOTE]
> This is just a personal fork. I can't guarantee you stability, because i'm only working on this when i've the time.

## What are the features of this fork?

There isn't much, but these are some features that i like:

* Upstream repository sync
> [!TIP]
> If you want to, you can disable the sync entirely from [workflow](../../../.github/workflows/sync.yml).
* Secret `client_id` token
> [!CAUTION]
> Even though the `client_id` token is hidden on the repository. The token can still be found by decompiling the generated APKs.
* Support replacing _signing keystore_
* Customize `options.json` file in `config.toml` **[TODO]**

## Why there are no releases like on the [j-hc repo](https://github.com/j-hc/revanced-magisk-module)?

It's kind of useless to continuously run the CI workflow when nobody will use the release APKs anyway. So unless there is other reasons, it'll probably stay that way.

Also this is only supposed to be a template repository, to use this you can create your own repository with the [template maker](https://github.com/new?template_name=rmm&template_owner=mementomoryn).

In case you have granted the access, you can also generate the template from these private repositories:

* [rv-builder](https://github.com/new?template_name=rv-builder&template_owner=mementomoryn)
* [rvx-builder](https://github.com/new?template_name=rvx-builder&template_owner=mementomoryn)
* [rvo-builder](https://github.com/new?template_name=rvo-builder&template_owner=mementomoryn)

## ReVanced surely discouraged pre-patched APKs, so what makes this one safe?

This repository is just a collection of _shell scripts_ to grab original APKs from **APKMirror**, **Uptodown**, and **Internet Archive**, then patch the grabbed APKs with **Patches**, **Integrations**, and **CLI** of your choice in `config.toml` using **GitHub Workflow Actions**.

If you're still not fully convinced, feel free to use the official way [here](https://revanced.app/).

## How to make feature requests or contributes to the repository?

I don't accept feature requests and code contributions, if you wanted to, you can simply do it [upstream](https://github.com/j-hc/revanced-magisk-module).
