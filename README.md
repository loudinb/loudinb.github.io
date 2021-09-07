# loudinb.github.io

![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/loudinb/loudinb.github.io)

<br />

This repo is for my [personal website](https://loudinb.github.io) which is hosted on GitHub Pages.  This is a static website built using [Jekyll](https://jekyllrb.com/) and the [al-folio](https://github.com/alshedivat/al-folio) theme.

<br />

### Local setup
This is a container-based development environment for Visual Studio Code and the Remote - Containers extension.

1. Download and intall [Docker Deskop](https://www.docker.com/products/docker-desktop).
2. Download and install [Visual Studio Code](https://code.visualstudio.com/download).
3. Install [Remote - Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) extension.
4. Clone this repo (`git clone https://github.com/loudinb/loudinb.github.io.gitß`).
5. Start VS Code, run the **Remote-Containers: Open Folder in Container...** command from the Command Palette (`F1`) or quick actions Status bar item, and select the repo folder cloned in the previous step.
<br />

### Deployment

<br />

---

### Notes on Container Configuration
* Base container image is Microsoft's Ubuntu image
* Add Ruby and other prerequisites by adding package installation instructions to the `Dockerfile` (see Jekyll [instructions](https://jekyllrb.com/docs/installation/ubuntu/)).

```dockerfile
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends ruby-full build-essential zlib1g-dev
```

* Install the jekyll and bundler gems by defining the GEM_HOME evironment variable and adding a run instruction to the `Dockerfile` (see Jekyll [instructions](https://jekyllrb.com/docs/installation/ubuntu/)).

```dockerfile
ENV GEM_HOME="/usr/local/gems"
ENV PATH=$GEM_HOME/bin:$PATH
RUN gem install jekyll bundler
```

<br />

### References
* Jekyll on Ubuntu [instructions](https://jekyllrb.com/docs/installation/ubuntu/)
* How to use [Jekyll tutorial](https://www.taniarascia.com/make-a-static-website-with-jekyll/).
ß

**For project pages (default):**

- Make changes, commit, and push!
- After deployment, the webpage will become available at `<your-github-username>.github.io/<your-repository-name>/`.
- The `master` branch should be used for the source code of your webpage and `gh-pages` branch (will be created on the first deployment) will be used for deployment.

**For personal and organization webpages:**
- Rename your repository to `<your-github-username>.github.io` or `<your-github-orgname>.github.io`.
- Click on **Actions** tab and **Enable GitHub Actions**; you no need to worry about creating any workflows as everything has already been set for you.
- Make sure the `url` and `baseurl` fields in `_config.yml` are empty.
- Make any other changes to your webpage, commit, and push. This will automatically trigger the **Deploy** action.
- Wait for a few minutes and let the action complete. You can see the progress in the **Actions** tab. If completed successfully, in addition to the `master` branch, your repository should now have a newly built `gh-pages` branch.
- Finally, in the **Settings**, in the Pages section, set the branch to `gh-pages` (**NOT** to `master`). See [Configuring a publishing source for your GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#choosing-a-publishing-source) for more details.
