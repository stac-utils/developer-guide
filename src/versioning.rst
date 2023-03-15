Versioning
==========

.. seealso::
    :class: sidebar

    This document originated as `an RFC in the stac-spec discussion boards
    <https://github.com/radiantearth/stac-spec/discussions/1184>`_. Some changes
    have been made to make the guidance more general, and not specific to Python
    packages.

.. note::
    :class: sidebar

    This document is structured like a `Rust RFC`_.

Summary
-------

All libraries in the `stac-utils`_ organization will have a consistent
versioning scheme based on `semantic versioning`_, with the caveat that it is
impossible to strictly adhere to that system. These projects will maintain a
hand-curated, meaningful CHANGELOG that provides useful information about the
changes contained in each release.

Motivation
----------

Semantic Versioning (SemVer) is a widely-used versioning scheme that is based on
three numbers, MAJOR, MINOR, and PATCH, each separated by a ``.`` (e.g.
``MAJOR.MINOR.PATCH``). SemVer is intended as a communication mechanism that
allows software developers to inform their users about breaking, non-breaking,
and bugfix changes to software.

While SemVer is nice in theory, in practice it is common for a "non-breaking"
release of a dependency to break one's code. The excellent `Semantic Versioning
Will Not Save You` outlines some of the pitfalls of relying on SemVer. However,
as the article states:

    This article is not about discouraging maintainers from using SemVer for
    their projects if they like it. There's nothing wrong about encoding the
    intent of a release into the version number as a service to its users.

This document describes the intent of MAJOR, MINOR, and PATCH releases for projects
in **stac-utils**, in the hopes that users can cautiously rely on those release
numbers in their downstream projects. While many projects are implicitly
implementing SemVer now, it is considered best practice to explicitly state a
project's versioning scheme. This document can be a single source of truth for the
versioning scheme for all projects that choose to implement it.

Guide-level explanation
-----------------------

The `Semantic Versioning Specification`_ will be used. It is not copied here in
full, but some key points are:

- MAJOR, MINOR, and PATCH are all non-negative integers without any leading
  zeros.
- PATCH changes indicate a backwards compatible bug fix.
- MINOR changes indicate backwards compatible functionality in the public API,
  deprecation of part of a public API, and substantial new functionality in
  private code.
- MAJOR changes indicate backwards incompatible changes to the public API.
- Version 1.0.0 defines the public API
- Initial development releases starting with "0.y.z" can treat changes in "y" as
  a major release, and "z" as a minor release. "0.0.z" releases are always major
  changes (taken from https://doc.rust-lang.org/cargo/reference/semver.html).

Projects are encouraged to stay in initial development (MAJOR == 0) until they
are willing to commit to a public API. In this way, we can engender some measure
of trust in the stability of MAJOR >= 1 **stac-utils** projects. At the
same time, projects in initial development are encouraged to create a public
roadmap to a 1.0.0 release.

Downstream users of **stac-utils** projects are well advised by Hynek
Schlawack's article (linked above):

    that's all SemVer is: a TL;DR of the changelog.

When new versions are released, users are encouraged to inspect the CHANGELOG
for information about what has changed, and how that might effect their systems.
Software maintainers will keep an up-to-date CHANGELOG with links to relevant
pull requests and issues, describing all changes and potential side effects.

.. _stac-utils: https://github.com/stac-utils
.. _semantic versioning: https://semver.org/
.. _semantic versioning will not save you: https://hynek.me/articles/semver-will-not-save-you/
.. _Rust RFC: https://github.com/rust-lang/rfcs/blob/c32adbda401bb01221a870b181028952e21da079/0000-template.md
.. _Semantic Versioning Specification: https://semver.org/#semantic-versioning-specification-semver
