## About
This app allows control of eVOLVER functions from your computer. It might be helpful for pump calibration and other tests before starting an experiment.

## Pre-Compiled Installation
- **If you have installation or compilation issues with this project, please see [the debugging guide](https://github.com/chentsulin/electron-react-boilerplate/issues/400)**
It is recommended to install via downloading an already compiled version of this program. To do this, go to https://github.com/FYNCH-BIO/evolver-electron/releases or click the releases button on the right side of the page. Download the correct installer for your OS and install.

Connect your computer to your eVOLVER and open the installed 'eVOLVER' app. Click the '+' in the lower right and add your eVOLVER's IP (found in the upper right hand corner on your machine).

## Instructions for Compiling
If for some reason you need to compile the eVOLVER app yourself, follow these instructions.

### Dependencies
Install dependencies with yarn.

```bash
$ cd your_directory/evolver-electron
$ yarn
```

### Run

Start the app in the `dev` environment. This starts the renderer process in [**hot-module-replacement**](https://webpack.js.org/guides/hmr-react/) mode and starts a webpack dev server that sends hot updates to the renderer process:

```bash
$ yarn dev
```
### Github

Use the command line to commit to the repo, using the Github App will throw errors:

```bash
git add .
git commit -a --no-verify -m "Put comment here"
```

### Packaging

To package apps for the local platform (Does not work well when compiling in other platforms. e.g. compile in OSX for OSX):

```bash
$ yarn package
```

To package app for Raspberry Pi, first simulate Pi with Docker container:

```bash
docker run --rm -ti  --env-file <(env | grep -iE 'DEBUG|NODE_|ELECTRON_|YARN_|NPM_|CI|CIRCLE|TRAVIS_TAG|TRAVIS|TRAVIS_REPO_|TRAVIS_BUILD_|TRAVIS_BRANCH|TRAVIS_PULL_REQUEST_|APPVEYOR_|CSC_|GH_|GITHUB_|BT_|AWS_|STRIP|BUILD_')  --env ELECTRON_CACHE="/root/.cache/electron" --env ELECTRON_BUILDER_CACHE="/root/.cache/electron-builder"  -v ${PWD}:/project  -v ${PWD##*/}-node-modules:/project/node_modules  -v ~/.cache/electron:/root/.cache/electron  -v ~/.cache/electron-builder:/root/.cache/electron-builder  electronuserland/builder:wine
```

Install dependencies again in environment. Remember to reinstall dependences for local platforms after exiting Docker.:

```bash
$ yarn
```

Package for Raspberry Pi:

```bash
$ yarn package-rpi
```

## Credit

- [Zachary Heins](https://github.com/zheins)
- [Brandon Wong](https://github.com/brandogw)
- [Electron-React Boilerplate Repo](https://github.com/electron-react-boilerplate/electron-react-boilerplate) - All this work is based on infrastructure from their repo
