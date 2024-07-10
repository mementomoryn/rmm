# 💡 How to create your own template?

 * Generate new repository with this [template](https://github.com/new?template_name=rv-builder&template_owner=mementomoryn)
 * Go to [Actions permissions](../../settings/actions), search for _Workflow permissions_ then:
   * Enable **Allow GitHub Actions to create and approve pull requests**
 * Go to [Actions secrets and variables](../../settings/secrets/actions) and create new repository secrets:
   * If you want to use `client_id` in `options.json`, `REDDIT_CLIENT_ID_OAUTH_TOKEN` with value of your [**Reddit API**](https://www.reddit.com/prefs/apps)
   * `WORKFLOW_TOKEN` with value of [**PAT**](https://github.com/settings/tokens) with a **_Workflow read & write_** permissions
   * If you want to replace [`ks.keystore`](./ks.keystore), `SIGN_KEYSTORE_INFO` with value of the keystore info
> [!NOTE]
> --keystore-entry-password=\<value\> --keystore-password=\<value\> --signer=mementomoryn --keystore-entry-alias=\<value\>
 * Customize [`config.toml`](./config.toml), for more info check [`CONFIG.md`](./CONFIG.md)
 * Customize [`options.json`](./options.json) based on `patches.json` of your ReVanced variant.
 * Run the build [workflow](../../actions/workflows/build.yml) to patch new releases