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
  * [Reddit Spoof Client ID](#reddit-spoof-client-id)
  * [Sign Keystore Info](#sign-keystore-info)
  * [Workflow Token](#workflow-token)

## Templates

To generate a new repository based on this template, you can use this:

[![rmm Template](https://img.shields.io/badge/rmm-Template-444444?style=for-the-badge&logo=github&labelColor=444444&color=222333)](https://github.com/new?template_name=rmm&template_owner=mementomoryn)

In case you have granted the access, you can also generate the template from these private repositories:

[![rv-builder Template](https://img.shields.io/badge/rv%20builder-Template-444444?style=for-the-badge&logo=github&labelColor=444444&color=222333)](https://github.com/new?template_name=rv-builder&template_owner=mementomoryn)

## Config & Options

Use this github pages by **j-hc** to generate both config and options easily:

[![RVMM Config Generator](https://img.shields.io/badge/RVMM%20Config-Generate-444444?style=for-the-badge&logo=github%20pages&labelColor=444444&color=222333)](https://j-hc.github.io/rvmm-config-gen/)

### CONFIG.toml
Open [`config.toml`](../config.toml), you can check [`CONFIG.md`](../CONFIG.md) for more info about how to set it up.

> [!TIP]
> You can use different custom `options.json` file per-app by adding this:
> 
> `options-file = "<name>.json"`
> 
> Defaults to `options.json`.

### OPTIONS.json
Open [`options.json`](../options.json), the _Key_ and _Value_ is based on `patches.json` of your ReVanced variant.

> [!TIP]
> Examples of `patches.json` URL: `https://github.com/<repo_owner>/<patches_repo>/blob/<main_branch>/patches.json`

Examples of how to create `<options_file>.json`:

```
[
  {
    "patchName": "<patch_name_1>",
    "options": [
      {
        "key": "<options_key_1>",
        "value": "<options_value_1>"
      },
      {
        "key": "<options_key_2>",
        "value": "<options_value_2>"
      }
    ]
  },
  {
    "patchName": "<patch_name_2>",
    "options": [
      {
        "key": "<options_key_1>",
        "value": "<options_value_1>"
      }
    ]
  }
]
```

## Workflows

### Build
Build APKs and send it to create new release.

You can manually run the build [workflow → run workflow](../../../actions/workflows/build.yml).

**Precautions**:
* `dlurl` Sources should not be rate-limited.
> [!NOTE]
> APKs may not able to be build, when not fulfilled. So it's recommended to add _fallback dlurl_.

* `<client_name>_CLIENT_ID` secrets value must be valid.
> [!CAUTION]
> APKs patched with _client-id spoof_ will not work fine, when not fulfilled.

* `<client_name>_CLIENT_ID` secrets must not be empty
> [!WARNING]
> Workflow `replace client-id` steps possibly skipped, when not fulfilled.

* `SIGN_KEYSTORE_INFO` secrets value must match the `ks.keystore` info.
> [!CAUTION]
> App signing process will fail, when not fulfilled.

* `SIGN_KEYSTORE_INFO` secrets must not be empty.
> [!WARNING]
> Workflow `replace keystore info` steps will be skipped, when not fulfilled.

### Template Sync
Sync the changes made on `mementomoryn/rmm` into your template repository by *pull request*.

Ignore files and folders from syncing with a [`.templatesyncignore`](../.templatesyncignore) file.

**Precautions**:

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

These secrets variables values are hidden and will not be able to be viewed, after you have created or edited it.

### Reddit Spoof Client ID
> [!NOTE]
> This secret variable is only mandatory if you want to use spoof client for third party reddit apps in `options.json`.

Secrets name that are already pre-configured on the workflow:
* Infinity: `INFINITY_CLIENT_ID`
* Sync: `SYNC_CLIENT_ID`
* Boost: `BOOST_CLIENT_ID`

The value is used to replace `client-id` value in `<options_file>.json` with the secrets.

Create your own **Reddit API** client ID [here](https://www.reddit.com/prefs/apps).

> [!IMPORTANT]
> The `application_type` has to be `installed app`
>
> The `redirect URI` value must match this:
> * Infinity: `infinity://localhost`
> * Sync: `http://redditsync/auth`
> * Boost: `http://rubenmayayo.com`
>
> More can be found [here](https://revanced.app/patches?s=Spoof+Client+ID).

Examples of how to use this on `<options_file>.json`:

```
[
  {
    "patchName": "Spoof client",
    "options": [
      {
        "key": "client-id",
        "value": "${<client_name>_CLIENT_ID}"
      }
    ]
  }
]
```

### Sign Keystore Info
> [!NOTE]
> This secret variable is only mandatory if you replace `ks.keystore` with your own.

Secrets name: `SIGN_KEYSTORE_INFO`

The value is used to replace the keystore info in `utils.sh`

> [!TIP]
> The value must follow this template:
>
> `--keystore-entry-password=<password> --keystore-password=<password> --signer=mementomoryn --keystore-entry-alias=<alias>`
>
> Examples of keystore following the template:
>
> `--keystore-entry-password=s3cur3p@ssw0rd --keystore-password=s3cur3p@ssw0rd --signer=mementomoryn --keystore-entry-alias=alias`

### Workflow Token
> [!NOTE]
> This secret variable is only mandatory if you want to use `template_sync.yml`.

Secrets name: `WORKFLOW_TOKEN`

The value is used to replace the `WORKFLOW_TOKEN` in `template_sync.yml`

Create your new **Personal Access Token** [here](https://github.com/settings/tokens?type=beta).

> [!IMPORTANT]
> **PAT** should have these permissions:
> * Actions: _read & write_
> * Contents: _read & write_
> * Metadata: _read_
> * Pull requests: _read & write_
> * Workflows: _read & write_
