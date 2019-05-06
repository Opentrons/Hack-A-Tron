---
layout: default
title: Development Setup
permalink: /development_setup
navigation_weight: 3
description: Read This Before Contributing
---

If you'd like to contribute (or maybe just run the very latest and greatest version of our API), this section details what you need to do to get your computer and local repository set up.

Individual projects may have additional instructions, so be sure to check out the various project `README`s, too.

### **Environment and Repository**

Your computer will need the following tools installed to be able to develop with the Opentrons platform:

* macOS 10.11+, Linux, or Windows 10

  * On Windows, please configure Git’s `core.autocrlf` setting (see the [Git config docs](https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration)) to `input` so that shell scripts required for the robot’s boot process in `api/opentrons/resources` do not have carriage returns inserted
  <br>
  <br>

* Python 3.6 ([pyenv](https://github.com/pyenv/pyenv) is optional, but recommended for macOS / Linux. If `pyenv` is not available for your system or you do not want to use it, you can set the environment variable `OT_PYTHON` to the full path to the Python 3.6 executable)



  ```shell
  pyenv install 3.6.4
  ```

* Node v8 LTS (Carbon) - [nvm](https://github.com/nvm-sh/nvm) is optional, but recommended

  ```shell
  nvm install lts/carbon
  ```

* [yarn](https://yarnpkg.com/en/docs/install#mac-stable) - JavaScript package manager

* [commitizen](https://github.com/commitizen/cz-cli) - Commit message formatter

  ```shell
  yarn global add commitizen
  ```

* GNU Make - we use [Makefiles](https://en.wikipedia.org/wiki/Makefile) to manage our builds

* cURL - used to push development updates to robots


Once you're set up, clone the repository and install all project dependencies:

```shell
git clone https://github.com/Opentrons/opentrons.git
cd opentrons
make install
```

In addition, if (and only if) you want to build a PDF version of the Opentrons API documentation, you must install a latex distribution that includes a callable pdflatex. If that is installed, you can do `make -C api docs-pdf`.
