# 💡 How to create your own template?

## Generate

To generate a new repository based on this template, you can open:



In case you have granted the access, you can also generate the template from these private repositories:


## Config & Options

### [`config.toml`](./config.toml)
Check [`CONFIG.md`](./CONFIG.md) for more info.

## [`options.json`](./options.json)
_Key_ and _Value_ is based on `patches.json` of your ReVanced variant.
> [!INFO]
> Examples of `patches.json` url
> https://github.com/\<repo_owner\>/\<patches_repo\>/patches.json

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