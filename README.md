scanctl
=======

**Note:** This project has been discontinued. 



> A tool to facilitate managing Whitesource data

![PyPi](https://img.shields.io/pypi/v/scanctl.svg)
![Travis](https://img.shields.io/travis/spotify/scanctl.svg)

### Requirements:

* Python 3.6
* Whitesource [Filesystem Agent][]

[Filesystem Agent]: https://whitesource.atlassian.net/wiki/spaces/WD/pages/33718339/File+System+Agent

### Development:

```sh
$ git clone git@github.com:spotify/scanctl.git
$ cd scanctl

# optionally create a virtualenv before installing
$ pyenv virtualenv 3.6.5 venv
$ pyenv activate venv

(venv) $ pip install -r requirements.txt
(venv) $ pip install -e .

# list all organizations and repositories from a remote
(venv) $ scanctl github --token $GITHUB_API_TOKEN list-orgs
(venv) $ scanctl github --token $GITHUB_API_TOKEN list-repos

# run a scan against a particular repository
(venv) $ scanctl scan --token $WHITESOURCE_API_TOKEN spotify/scanctl
```

### Release:

Follow the standard pull request workflow; tests will be run before merging.
Either as part of the pull request or as a commit to master, run the following
commands to increment the release version:

```sh
(venv) $ pip install -r requirements-dev.txt
(venv) $ bumpversion minor
(venv) $ git push && git push --tags
```

The next travis build will push the new package to PyPi.

### Code of Conduct

This project adheres to the [Open Code of Conduct][code-of-conduct]. By
participating, you are expected to honor this code.

[code-of-conduct]: https://github.com/spotify/code-of-conduct/blob/master/code-of-conduct.md
