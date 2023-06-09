Tooling
=======

By sharing the same tooling stack among our projects, we make it easier for
developers to move from repository to repository.
Not every repository will use or need all of these tools.

CHANGELOG
---------

All projects should keep a changelog, following the guidelines of `keep a changelog`_.

pre-commit
----------

We use `pre-commit`_ extensively to automatically lint, format, and check code
on developer's machines and in :abbr:`CI (Continuous Integration)`.  For Python
projects, **pre-commit** should be configured to use the same version of tools
that are defined in ``requirements-dev.txt``.

Documentation
-------------

`Sphinx`_ is recommended if the primary language doesn't provide standard
documentation tool (e.g. don't use Sphinx for Rust projects). This developer
guide is built with Sphinx.

.. _Sphinx: https://www.sphinx-doc.org/en/master/
.. _keep a changelog: https://keepachangelog.com/en/1.0.0/
