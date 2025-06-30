# gw2load/manifest

This repository holds all the data used to generate a manifest of gw2load compatible addons for the [GW2 Addon Manager](https://github.com/gw2load/GW2AddonManager).
The manifest is generated using [gw2load/generate-manifest-action](https://github.com/gw2load/generate-manifest-action) and available at https://gw2load.github.io/manifest/manifest.json.


## Add your addon

If your addon is compatible with gw2load (or ArcDPS) and you would like it to be available through the Addon Manager, follow these steps:

1. [Fork](https://docs.github.com/en/github/getting-started-with-github/quickstart/fork-a-repo) this repository.

2. Add a new `.toml` file in the [addons](./addons/) directory using this schema:

    ```toml
    # General information about your addon
    [package]
    id = "<unique id of your addon>"
    name = "<name of your addon>"
    description = "<description of your addon>"
    tooltip = "<tooltip of your addon>"
    website = "<website of your addon>"
    developer = "<developer of your addon>"
    issue_tracker = "<optional issue tracker of your addon>"
    vcs = "<optional source repository url of your addon>"

    # Dependency information
    dependencies = ["<optional array of required dependency addons>"]
    optional_dependencies = ["<optional array of optional dependency addons>"]
    conflicts = ["<optional array of known addon conflicts>"]

    # Hosting configuration used to automatically update your addon
    # Choose either `host.github` or `host.standalone`
    [host.github]
    url = "<org/repo>"

    [host.standalone]
    url = "<url of your addon dll>"
    version_url = "<url returning your current version>"
    prerelease_url = "<optional url of your prerelease addon dll>"
    prerelease_version_url = "<optional url returning your current prerelease version>"

    # Installation mode
    [installation]
    mode = "gw2load" # for addons natively loaded by gw2load
    mode = "arc"     # for addons loaded through ArcDPS
    ```

3. Submit a [Pull Request](https://docs.github.com/en/github/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests).


## License

Licensed under the [MIT License](./LICENSE).
