# 💡 How to create your own template?

## Templates

To generate a new repository based on this template, you can use this:

[![rmm Template](https://img.shields.io/badge/rmm-Template-444444?style=for-the-badge&logo=github&labelColor=444444&color=222333)](https://github.com/new?template_name=rmm&template_owner=mementomoryn)

In case you have granted the access, you can also generate the template from these private repositories:

[![rv-builder Template](https://img.shields.io/badge/rv%20builder-Template-444444?style=for-the-badge&logo=github&labelColor=444444&color=222333)](https://github.com/new?template_name=rv-builder&template_owner=mementomoryn)

## Config & Options

### CONFIG.toml
Open [`config.toml`](../config.toml), you can check [`CONFIG.md`](./CONFIG.md) for more info about how to set it up.

### OPTIONS.json
Open [`options.json`](../options.json), the _Key_ and _Value_ is based on `patches.json` of your ReVanced variant.

> [!TIP]
> Examples of `patches.json` URL: `https://github.com/<repo_owner>/<patches_repo>/patches.json`

You also can generate both config and options with this generator:

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

> [!IMPORTANT]
> The redirect URI must match with third party reddit apps you want to patch.

### SIGN_KEYSTORE_INFO
The value is used to replace the keystore info in `utils.sh`

### WORKFLOW_TOKEN
The value is used to replace the `WORKFLOW_TOKEN` in `template_sync.yml`

Create your new **Personal Access Token** [here](https://github.com/settings/tokens?type=beta).

> [!IMPORTANT]
> Give the PAT these permissions:
> * _Actions_: read & write

 * Go to [Actions secrets and variables](../../settings/secrets/actions) and create new repository secrets:
   * If you want to use `client_id` in `options.json`, `REDDIT_CLIENT_ID_OAUTH_TOKEN` with value of your [**Reddit API**](https://www.reddit.com/prefs/apps)
   * `WORKFLOW_TOKEN` with value of [**PAT**](https://github.com/settings/tokens) with a **_Workflow read & write_** permissions
   * If you want to replace [`ks.keystore`](./ks.keystore), `SIGN_KEYSTORE_INFO` with value of the keystore info
> [!NOTE]
> --keystore-entry-password=\<value\> --keystore-password=\<value\> --signer=mementomoryn --keystore-entry-alias=\<value\>