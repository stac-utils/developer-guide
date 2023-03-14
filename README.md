# The stac-utils developer guide

[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-2.1-4baaaa.svg?style=for-the-badge)](./CODE_OF_CONDUCT)

This book is meant as a reference for developers working on repos in the [stac-utils organization](https://github.com/stac-utils).
Its rendered content is available at <https://stac-utils.github.com/developer-guide>.

## Contributing

Install the development requirements:

```shell
pip install -r requirements-dev.txt
```

The book's source is located in [src/](./src/).
To build the documentation as html pages:

```shell
make html
```

While writing, it can be easiest to rebuild the html documentation as you write:

```shell
make livehtml
```

This will start a documentation server at <http://127.0.0.1:8000/>.

### Updating dependencies

We use [pip-tools](https://github.com/jazzband/pip-tools) to generate our [requirements.txt](./requirements.txt) file.
To add, edit, or remove a dependency, change [requirements.in](./requirements.in).
Then:

```shell
pip-compile requirements.in
```

To update dependency versions:

```shell
pip-compile --upgrade requirements.in
```

To add, edit, or remove a development dependency (used for writing, but not used for building), edit [requirements-dev.txt](./requirements-dev.txt).
You may need to update [.pre-commit-config.yaml](./.pre-commit-config.yaml) as well to match versions (e.g. if you update the [black](https://github.com/psf/black) version).
