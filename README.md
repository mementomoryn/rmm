<div align="center">

[<img src="https://raw.githubusercontent.com/ReVanced/revanced-patches/main/assets/revanced-logo/revanced-logo.svg" width="150px"/>](../../)

# ReVanced Auto Builder

Automatically build APKs with patches of [ReVanced](https://github.com/ReVanced/revanced-patches) or [forks](https://github.com/ReVanced/revanced-patches-template/forks?include=active%2Cnetwork&page=1&period=&sort_by=stargazer_counts) when there is new update available.

<br>

## Activity

<br>

[![GitHub Pulls](https://img.shields.io/badge/Pulls-Link-444444?style=for-the-badge&logo=github&label=Pulls&labelColor=444444&color=9858B8)](../../pulls)

[![GitHub Forks](https://img.shields.io/badge/Forks-Link-444444?style=for-the-badge&logo=github&label=Forks&labelColor=444444&color=9858B8)](../../forks)

[![GitHub Commits](https://img.shields.io/badge/Commits-Link-444444?style=for-the-badge&logo=github&label=Commits&labelColor=444444&color=9858B8)](../../commits)

[![GitHub Stargazers](https://img.shields.io/badge/Stargazers-Link-444444?style=for-the-badge&logo=github&label=Stargazers&labelColor=444444&color=9858B8)
](../../stargazers)

<br>

## Workflow

<br>

[![GitHub Actions Workflow Upstream](https://img.shields.io/github/actions/workflow/status/mementomoryn/rmm/sync.yml?branch=main&style=for-the-badge&logo=github%20actions&logoColor=FFFFFF&label=Upstream&labelColor=444444&color=405898)
](https://github.com/mementomoryn/rmm/actions/workflows/sync.yml)

[![GitHub Actions Workflow Template](https://img.shields.io/badge/Template-Status-444444?style=for-the-badge&logo=github%20actions&logoColor=FFFFFF&label=Template&labelColor=444444&color=405898)
](../../actions/workflows/template_sync.yml)

[![GitHub Actions Workflow Build](https://img.shields.io/badge/CI-Status-444444?style=for-the-badge&logo=github%20actions&logoColor=FFFFFF&label=Build&labelColor=444444&color=405898)
](../../actions/workflows/build.yml)

[![GitHub Actions Workflow CI](https://img.shields.io/badge/CI-Status-%23444444?style=for-the-badge&logo=github%20actions&logoColor=FFFFFF&label=CI&labelColor=444444&color=405898)
](../../actions/workflows/ci.yml)

<br>

## Installation

<br>

[![GitHub Release](https://img.shields.io/badge/GitHub-Release-444444?style=for-the-badge&logo=github&logoColor=white&labelColor=222333)
](../../releases)

[![Obtainium Release](https://img.shields.io/github/v/release/imranr98/obtainium?sort=date&display_name=release&style=for-the-badge&logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAC0AAAAtCAYAAAA6GuKaAAAAAXNSR0IArs4c6QAAAARzQklUCAgICHwIZIgAAALHSURBVFiF7Zg9a1RBFIbfY+JXNMZGEQU1KbQKNmoshFRBLEJiqYKCIAgW+g8sFCws8gdsLIyI4oIEW1cIRvALwZQmsZBA/FpTaEIIj8V19eZm9s7cm5tdCft0O5zzzjuHM7MzV2rSZG1h9Z4QaJN098/cmNmpensIAjgC9OLmE3AcqHsBnQCHgUlgvobhKovAZKPNXvGYTGMIONEI05MrMF3lNrB+NcyVgJJjvK8A0wAvgesrNXmAaEPNJcRvOmK/FWS8yp6q9rpAszuJNsorSWVJGxMhmxxpt8LLEcRsUBRwMbQMjtyeAqs8FNeueTYCrZIWMlSiy8yWHFuuxeQASZ1m9rE6kNYeDzOKv3GMnc2o4WJc0kx8wGka6JDUk1F8K9CbGBuRNB/7PadoT5Qz6I6a2S9vFLX/cn0MJHQMeEJ02hwjdgJk0GwJWhpwJ6fpeb+6BDwI1Lvnyl/WHsBmSeeCVpdI1dJWqGXYJLUF6g2HzQz3c1T4MdBPtBd8+h2BmrPAdpdGa0KwRdLuoNVFPJJ0wcx+ZMgpB8Y9M7OKNypDFao4e84zRxBZBIczmoborjwYqB96ZR1L00luxNPBK/zHBkkloIK/p3cFapaDooCTOarsogTsqDFHKKlnc7zSXySNBlYijUFJM0QvkPaY4Q+B+S/MbDEtYMmFiegM3StpKqPRWkxLOi/ps6Qxua+wSfbHL0fBEP39XgWmC2qZUMaBLT5/3mc78FVSu6Ti32vLGTGzfl9Q0LcG4KikPkk3Vuoq1YxZ8d8+iJ5d71epNd4WbjhmvA3oXgXTA/7Zi1nANeB7AYYrRLfL+gFcYvlnhSxM1dVwzHg38DyP44YYTpg/BDzN4Pl1oz3/BegMND3kV6sjQAtwGVj4b1sjDeAd8DPhecaf2WCALuBMzPS+PDqt/pDiMLMJSRPANkkHc93mmjRZg/wGMhSvjoAjfIkAAAAASUVORK5CYII=&logoColor=white&label=Obtainium&labelColor=4828A0&color=444444)
](https://github.com/ImranR98/Obtainium/releases)

[![GMSCore Release](https://img.shields.io/github/v/release/revanced/gmscore?sort=date&display_name=release&style=for-the-badge&logo=google&logoColor=white&label=GMS%20Core&labelColor=2F9088&color=444444)
](https://github.com/ReVanced/GmsCore/releases)

</div>

<br>

## Use your own configurations

 * Generate new repository with this [template](https://github.com/new?template_name=rv-builder&template_owner=mementomoryn)
 * Go to [Actions permissions](../../settings/actions), search for _Workflow permissions_ then:
   * Enable **Allow GitHub Actions to create and approve pull requests**
 * Go to [Actions secrets and variables](../../settings/secrets/actions) and create new repository secrets:
   * `REDDIT_CLIENT_ID_OAUTH_TOKEN` with value of your own [**Reddit API**](https://www.reddit.com/prefs/apps), or leave the value empty if you don't want to use `client_id` on `options.json`
   * `WORKFLOW_TOKEN` with value of your [**PAT**](https://github.com/settings/tokens) with a **_Workflow read & write_** permissions
   * `SIGN_KEYSTORE_INFO` with value of
&nbsp;&nbsp;
```
--keystore-entry-password=<value> --keystore-password=<value> --signer=mementomoryn --keystore-entry-alias=<value>
```
 * Customize [`config.toml`](./config.toml), for more info check [`CONFIG.md`](./CONFIG.md)
 * Customize [`options.json`](./options.json) based on `patches.json` of your ReVanced variant.
 * Run the build [workflow](../../actions/workflows/build.yml) to patch new releases
