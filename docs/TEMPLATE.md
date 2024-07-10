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

## Workflows

### Build
Build APKs and send it to create new release.

You can manually run the build [workflow → run workflow](../../../actions/workflows/build.yml).

Configurations:
* `REDDIT_CLIENT_ID_OAUTH_TOKEN` secrets is empty
* SIGN_KEYSTORE_INFO secrets is empty

### Template Sync
Sync the changes made on `mementomoryn/rmm` into your template repository by *pull request*.

**Configurations**:
* Enabling **Allow GitHub Actions to create and approve pull requests** on [Actions permissions → Workflow permissions](../../../settings/actions).
  * > [!CAUTION]
  * > The workflow will not be able to create pull request for the synced changes.
* `WORKFLOW_TOKEN` does not have `workflow read & write` permissions.
> [!CAUTION]
> The workflow will not be able to sync changes made to the files inside `.github/workflows` folder.
* `WORKFLOW_TOKEN` secrets is empty.
> [!WARNING]
> All workflow steps will be skipped.


## Secrets

### REDDIT_CLIENT_ID_OAUTH_TOKEN

### SIGN_KEYSTORE_INFO

### WORKFLOW_TOKEN

 * Go to [Actions secrets and variables](../../settings/secrets/actions) and create new repository secrets:
   * If you want to use `client_id` in `options.json`, `REDDIT_CLIENT_ID_OAUTH_TOKEN` with value of your [**Reddit API**](https://www.reddit.com/prefs/apps)
   * `WORKFLOW_TOKEN` with value of [**PAT**](https://github.com/settings/tokens) with a **_Workflow read & write_** permissions
   * If you want to replace [`ks.keystore`](./ks.keystore), `SIGN_KEYSTORE_INFO` with value of the keystore info
> [!NOTE]
> --keystore-entry-password=\<value\> --keystore-password=\<value\> --signer=mementomoryn --keystore-entry-alias=\<value\>
 * 
 * 
 * Run the build [workflow](../../actions/workflows/build.yml) to patch new releases