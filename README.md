dockerhub-semantic-release-gh-action
===
[![LICENSE](https://img.shields.io/github/license/timo-reymann/dockerhub-semantic-release-gh-action)](https://github.com/timo-reymann/dockerhub-semantic-release-gh-action/blob/main/LICENSE)

<p align="center">
	<img width="300" src="https://avatars.githubusercontent.com/u/54465427?v=4">
    <br />
    Utilize semantic-release and publish images to docker hub automatically
</p>

## Required for usage

- docker hub account
- Dockerfile is present in root folder
- Token for pushing and updating the repo on docker hub


## Usage

```yaml
name: Continuous build and release docker image
on:
  push:
    branches:
      - master
      - main
permissions:
  contents: write
jobs:
  main:
    steps:
      - runs-on: ubuntu-latest
        uses: timo-reymann/docker-semantic-release-gh-action@v1
        with:
          image: user/imagename
          dockerhub_username: ${{ secrets.DOCKERHUB_USERNAME }}
          dockerhub_token: ${{ secrets.DOCKERHUB_TOKEN }}
          github_token: ${{ secrets.GITHUB_TOKEN }}
```

