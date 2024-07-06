<div align="center">

[<img src="https://raw.githubusercontent.com/ReVanced/revanced-patches/main/assets/revanced-logo/revanced-logo.svg" width="150px"/>](../../)

# ReVanced Auto Builder

Automatically build APKs with patches of [ReVanced](https://github.com/ReVanced/revanced-patches) or [forks](https://github.com/ReVanced/revanced-patches-template/forks?include=active%2Cnetwork&page=1&period=&sort_by=stargazer_counts) when there is new update available.

<br>

## Activity

<br>

[![GitHub Commits](https://img.shields.io/badge/Commits-Link-%23444444?style=for-the-badge&logo=github&label=Commits&labelColor=%23444444&color=%239858B8)](../../commits)

[![GitHub Forks](https://img.shields.io/badge/Forks-Link-%23444444?style=for-the-badge&logo=github&label=Forks&labelColor=%23444444&color=%239858B8)](../../forks)

[![GitHub Pulls](https://img.shields.io/badge/Pulls-Link-%23444444?style=for-the-badge&logo=github&label=Pulls&labelColor=%23444444&color=%239858B8)](../../pulls)

[![GitHub Stargazers](https://img.shields.io/badge/Stargazers-Link-%23444444?style=for-the-badge&logo=github&label=Stargazers&labelColor=%23444444&color=%239858B8)
](../../stargazers)

[![GitHub Release](https://img.shields.io/badge/Releases-Link-%23444444?style=for-the-badge&logo=github&label=Releases&labelColor=%23444444&color=%239858B8)
](../../releases)

<br>

## Workflow

<br>

[![GitHub Actions Workflow Upstream](https://img.shields.io/github/actions/workflow/status/mementomoryn/rmm/sync.yml?branch=main&style=for-the-badge&logo=github%20actions&logoColor=%23FFFFFF&label=Upstream&labelColor=%23444444&color=%23405898)
](https://github.com/mementomoryn/rmm/actions/workflows/sync.yml)

[![GitHub Actions Workflow Template](https://img.shields.io/badge/Template-Status-%23444444?style=for-the-badge&logo=github%20actions&logoColor=%23FFFFFF&label=Template&labelColor=%23444444&color=%23405898)
](../../actions/workflows/template_sync.yml)

[![GitHub Actions Workflow Build](https://img.shields.io/badge/CI-Status-%23444444?style=for-the-badge&logo=github%20actions&logoColor=%23FFFFFF&label=Build&labelColor=%23444444&color=%23405898)
](../../actions/workflows/build.yml)

[![GitHub Actions Workflow CI](https://img.shields.io/badge/CI-Status-%23444444?style=for-the-badge&logo=github%20actions&logoColor=%23FFFFFF&label=CI&labelColor=%23444444&color=%23405898)
](../../actions/workflows/ci.yml)

</div>

<br>

## How to use your own configurations

 * Generate new repository with this [template](https://github.com/new?template_name=rv-builder&template_owner=mementomoryn)
 * Customize [`config.toml`](./config.toml), for more info check [`CONFIG.md`](./CONFIG.md)
 * Customize [`options.json`](./options.json) based on `patches.json`
 * Replace `ks.keystore` with your own
   * Update keystore info at line `309 patch_apk()` in [`utils.sh`](./utils.sh)
 * Go to [Actions permissions](../../settings/actions), search for _Workflow permissions_ then:
   * Enable **Allow GitHub Actions to create and approve pull requests**
 * Go to [Actions secrets and variables](../../settings/secrets/actions) and create new repository secrets:
   * `REDDIT_CLIENT_ID_OAUTH_TOKEN` with value of your own [**Reddit API**](https://www.reddit.com/prefs/apps), or leave the value empty if you don't want to use `client_id` on `options.json`
   * `WORKFLOW_TOKEN` with value of your [**PAT**](https://github.com/settings/tokens) with a **_Workflow read & write_** permissions
 * Run the build [workflow](../../actions/workflows/build.yml)
 * Grab the APKs from [releases](../../releases)