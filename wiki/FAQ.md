## What is this repository?

This is a fork based on [j-hc/revanced-magisk-module repo](https://github.com/j-hc/revanced-magisk-module) with little twists & improvements of my own.

## What are the differences of this fork?

There is not much, but these are some differences that i like:

* Upstream repository sync
* Secret `client_id` token
> [!CAUTION]
> Even though the `client_id` token is unavailable on the repository. The token can still be found by decompiling the generated APKs.
* Support replacing _signing keystore_

## Why there are no releases unlike on the [j-hc repo](https://github.com/j-hc/revanced-magisk-module)?

This is only supposed to be a template repository, to use this you need to create your own repository with the [template maker](https://github.com/new?template_name=rmm&template_owner=mementomoryn).

In case you have granted the access, you can also generate the template from these repositories:

## ReVanced certainly discouraged pre-patched APKs, so what makes this one safe?

This repository is just a collection of _shell scripts_ to grab original APKs from **APKMirror**, **Uptodown**, and **Internet** Archive then patch the grabbed APKs with **Patches**, **Integrations**, and **CLI** of your choice using **GitHub Workflow Actions**.

If you are still not convinced, feel free to use the official way [here](https://revanced.app/).