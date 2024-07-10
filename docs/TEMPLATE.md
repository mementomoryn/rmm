# 💡 How to create your own template?

## Templates

To generate a new repository based on this template, you can use:

[![rmm Template](https://img.shields.io/badge/rmm-Template-444444?style=for-the-badge&logo=github&labelColor=444444&color=222333)](https://github.com/new?template_name=rmm&template_owner=mementomoryn)

In case you have granted the access, you can also generate the template from these private repositories:

[![rv-builder Template](https://img.shields.io/badge/rv%20builder-Template-444444?style=for-the-badge&logo=github&labelColor=444444&color=222333)](https://github.com/new?template_name=rv-builder&template_owner=mementomoryn)

## Config & Options

### CONFIG.toml
Check [`CONFIG.md`](./CONFIG.md) for more info about how to set it up. Open [CONFIG.toml](../config.toml)

### OPTIONS.json
_Key_ and _Value_ is based on `patches.json` of your ReVanced variant. Open [OPTIONS.json](../options.json)
> [!NOTE]
> Examples of `patches.json` URL: `https://github.com/<repo_owner>/<patches_repo>/patches.json`

## Workflows

### Build

### Template Sync

## Secrets

### REDDIT_CLIENT_ID_OAUTH_TOKEN

### SIGN_KEYSTORE_INFO

### WORKFLOW_TOKEN

 * Go to [Actions permissions](../../settings/actions), search for _Workflow permissions_ then:
   * Enable **Allow GitHub Actions to create and approve pull requests**
 * Go to [Actions secrets and variables](../../settings/secrets/actions) and create new repository secrets:
   * If you want to use `client_id` in `options.json`, `REDDIT_CLIENT_ID_OAUTH_TOKEN` with value of your [**Reddit API**](https://www.reddit.com/prefs/apps)
   * `WORKFLOW_TOKEN` with value of [**PAT**](https://github.com/settings/tokens) with a **_Workflow read & write_** permissions
   * If you want to replace [`ks.keystore`](./ks.keystore), `SIGN_KEYSTORE_INFO` with value of the keystore info
> [!NOTE]
> --keystore-entry-password=\<value\> --keystore-password=\<value\> --signer=mementomoryn --keystore-entry-alias=\<value\>
 * 
 * 
 * Run the build [workflow](../../actions/workflows/build.yml) to patch new releases