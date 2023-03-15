Pull request
============

This file should live at ``.github/pull_request_template.md``.
Note that the list under "Related issues(s)" is important for activating `closing keywords`_.

.. code-block:: markdown

    ## Related issue(s)

    - Closes #

    ## Description

    ## PR Checklist

    - [ ] `pre-commit` hooks pass locally
    - [ ] Tests pass (run `scripts/test`)
    - [ ] Documentation has been updated to reflect changes, if applicable
    - [ ] This PR maintains or improves overall codebase code coverage.
    - [ ] Changes are added to the [CHANGELOG](https://github.com/stac-utils/pystac/blob/main/CHANGELOG.md). See [the docs](https://pystac.readthedocs.io/en/latest/contributing.html#changelog) for information about adding to the changelog.

.. _closing keywords: https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue#about-linked-issues-and-pull-requests
