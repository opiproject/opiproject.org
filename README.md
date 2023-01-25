# Open Programmable Infrastructure Project Website

[![Linters](https://github.com/opiproject/opiproject.org/actions/workflows/linters.yml/badge.svg)](https://github.com/opiproject/opiproject.org/actions/workflows/linters.yml)
[![github pages](https://github.com/opiproject/opiproject.org/actions/workflows/gh-pages.yml/badge.svg)](https://github.com/opiproject/opiproject.org/actions/workflows/gh-pages.yml)
[![pages-build-deployment](https://github.com/opiproject/opiproject.org/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/opiproject/opiproject.org/actions/workflows/pages/pages-build-deployment)

Hugo code for OPI Project website.

## Development

There are two ways to test this out:

* Install hugo locally
* Use a pre-built docker image with hugo

### Install Hugo Locally

To work on the website, make sure you have hugo installed. You can do that by
following the instructions [here](https://gohugo.io/getting-started/installing/).

Once you have hugo installed, you can make changes to the website. To see
them locally, run the following in the root directory of the website:

```code
hugo server --disableFastRender
```

### Docker Image With Hugo

This method requires you to use a Docker image with hugo pre-built and installed
inside. [This image](https://hub.docker.com/r/klakegg/hugo/) works well for this
purpose.

```code
docker run --user=$(id -u):$(id -g) --rm -it   -v $(pwd):/src   -p 1313:1313   klakegg/hugo:0.107.0-ext-ubuntu   server --disableFastRender
```

## Development Output

Once you have hugo running by either installing it locally or using a Docker
image, this should give you something like the following as output:

```code
➜  opiproject.org git:(dev) ✗ hugo server --disableFastRender
Start building sites …
hugo v0.101.0+extended darwin/amd64 BuildDate=unknown

                   | EN
-------------------+-----
  Pages            | 18
  Paginator pages  |  0
  Non-page files   |  0
  Static files     | 41
  Processed images |  0
  Aliases          |  1
  Sitemaps         |  1
  Cleaned          |  0

Built in 170 ms
Watching for changes in /Users/kmestery/git/OPI/opiproject.org/{archetypes,content,data,layouts,static,themes}
Watching for config changes in /Users/kmestery/git/OPI/opiproject.org/config.toml, /Users/kmestery/git/OPI/opiproject.org/themes/ananke/config.yaml
Environment: "development"
Serving pages from memory
Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)
Press Ctrl+C to stop
```

You can then browse to `http://localhost:1313/` to see your local changes.
