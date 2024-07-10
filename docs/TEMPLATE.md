# 💡 How to create your own template?

## 📜 Table of contents

* [Templates](#templates)
* [Config & Options](#config--options)
  * [CONFIG.toml](#configtoml)
  * [OPTIONS.json](#optionsjson)
* [Workflows](#workflows)
  * [Build](#build)
  * [Template Sync](#template-sync)
* [Secrets](#secrets)
  * [REDDIT_CLIENT_ID_OAUTH_TOKEN](#reddit_client_id_oauth_token)
  * [SIGN_KEYSTORE_INFO](#sign_keystore_info)
  * [WORKFLOW_TOKEN](#workflow_token)

## Templates

To generate a new repository based on this template, you can use this:

[![rmm Template](https://img.shields.io/badge/rmm-Template-444444?style=for-the-badge&logo=github&labelColor=444444&color=222333)](https://github.com/new?template_name=rmm&template_owner=mementomoryn)

In case you have granted the access, you can also generate the template from these private repositories:

[![rv-builder Template](https://img.shields.io/badge/rv%20builder-Template-444444?style=for-the-badge&logo=github&labelColor=444444&color=222333)](https://github.com/new?template_name=rv-builder&template_owner=mementomoryn)

[![rvx-builder Template](https://img.shields.io/badge/rvx%20builder-Template-444444?style=for-the-badge&logo=github&labelColor=444444&color=222333)](https://github.com/new?template_name=rvx-builder&template_owner=mementomoryn)

[![rvo-builder Template](https://img.shields.io/badge/rvo%20builder-Template-444444?style=for-the-badge&logo=github&labelColor=444444&color=222333)](https://github.com/new?template_name=rvo-builder&template_owner=mementomoryn)

## Config & Options

### CONFIG.toml
Open [`config.toml`](../config.toml), you can check [`CONFIG.md`](./CONFIG.md) for more info about how to set it up.

### OPTIONS.json
Open [`options.json`](../options.json), the _Key_ and _Value_ is based on `patches.json` of your ReVanced variant.

> [!TIP]
> Examples of `patches.json` URL: `https://github.com/<repo_owner>/<patches_repo>/patches.json`

You can also generate both config and options with this website:

[![RVMM Config Generator](https://img.shields.io/badge/RVMM%20Config-Generate-444444?style=for-the-badge&logo=github%20pages&labelColor=444444&color=222333)](https://j-hc.github.io/rvmm-config-gen/)

## Workflows

### Build
Build APKs and send it to create new release.

You can manually run the build [workflow → run workflow](../../../actions/workflows/build.yml).

Configurations:
* `REDDIT_CLIENT_ID_OAUTH_TOKEN` secrets must not be empty
> [!WARNING]
> Build workflow `replace client_id` steps will be skipped, when not fulfilled.

* `SIGN_KEYSTORE_INFO` secrets must not be empty.
> [!WARNING]
> Build workflow `replace keystore info` steps will be skipped, when not fulfilled.

### Template Sync
Sync the changes made on `mementomoryn/rmm` into your template repository by *pull request*.

**Configurations**:

* Enabling **Allow GitHub Actions to create and approve pull requests** on [Actions permissions → Workflow permissions](../../../settings/actions).
> [!CAUTION]
> The workflow will not be able to create pull request for the synced changes, when not fulfilled.

* `WORKFLOW_TOKEN` does not have `workflow read & write` permissions.
> [!CAUTION]
> The workflow will not be able to sync changes made to the files inside `.github/workflows` folder, when not fulfilled.

* `WORKFLOW_TOKEN` secrets must not be empty.
> [!WARNING]
> All workflow steps will be skipped, when not fulfilled.

## Secrets

Go to [Actions secrets and variables](../../../settings/secrets/actions) and create new repository secrets.

These secrets variables values are hidden and will not be able to be viewed, after you create or edit it.

### REDDIT_CLIENT_ID_OAUTH_TOKEN
The value is used to replace the `client_id` in `options.json`.

Create your own **Reddit API** token [here](https://www.reddit.com/prefs/apps).

This secret variable is only mandatory if you want to use spoof client for third party reddit apps in `options.json`.

> [!IMPORTANT]
> The redirect URI must match with third party reddit apps you want to patch.

### SIGN_KEYSTORE_INFO
The value is used to replace the keystore info in `utils.sh`

This secret variable is only mandatory if you want to replace `ks.keystore` with your own.

> [!TIP]
> The value must follow this template:
>
> `--keystore-entry-password=<password> --keystore-password=<password> --signer=mementomoryn --keystore-entry-alias=<alias>`
>
> Keystore info examples:
>
> `--keystore-entry-password=s3cur3p@ssw0rd --keystore-password=s3cur3p@ssw0rd --signer=mementomoryn --keystore-entry-alias=alias`

### WORKFLOW_TOKEN
The value is used to replace the `WORKFLOW_TOKEN` in `template_sync.yml`

Create your new **Personal Access Token** [here](https://github.com/settings/tokens?type=beta).

This secret variable is only mandatory if you want to use `template_sync.yml`.

> [!IMPORTANT]
> Give the **PAT** these permissions:
> * Actions: _read & write_
> * Contents: _read & write_
> * Metadata: _read_
> * Pull requests: _read & write_
> * Workflows: _read & write_