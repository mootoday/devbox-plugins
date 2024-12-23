# devbox-plugins

A collection of Devbox plugins for various open source projects to standardize development environments.

## Prerequisites

Install [Devbox](https://github.com/jetify-com/devbox):

```bash
curl -fsSL https://get.jetify.com/devbox | bash
```

## Getting started

For any open source project, first check if a config exists in this repo at `plugins/github/<owner>/<repo>`. If not, please open an issue on GitHub and I'll look into it.

If a config exists:

1. Clone the specific project with `git clone git@github.com:<owner>/<repo>.git`
1. Navigate to the repo source code:
    ```bash
    cd <repo>
    ```
1. Initialize Devbox:
    ```bash
    devbox init
    ```
1. Configure the project's plugin:
    ```bash
    REPO="<owner>/<repo>" && echo "{\"include\":[\"github:mootoday/devbox-plugins/refs/heads/main?dir=plugins/github/$REPO\"]}" > devbox.json && unset REPO
    ```
1. Start the dev environment:
    ```bash
    devbox services up
    ```

If you wish to work in a shell that inludes all required project dependencies, but without building and starting the dev environment, you can use the following command:

```bash
devbox shell
```

## Missing project configuration

If a project configuration is missing in `./plugins/github/`, please open a GitHub issue with a link to the GitHub repo. We'll prioritize based on 👍 emojis on an issue's description.
