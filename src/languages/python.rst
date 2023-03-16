Python
======

Guidelines for setting up and working in Python projects.

Dependencies
------------

If your project is a application, e.g. a :abbr:`CLI (Command Line Interface)` or
a deployed service such as a AWS Lambda function, you should pin all your
dependencies to exact versions. Tools such as `pip-tools`_ can help with the
process; this documentation uses **pip-tools** to defines its dependencies.

.. seealso::
   :class: sidebar

   For more information about the rationale behind these recommendations, and
   some examples of how you might set up CI checks in Github actions for this
   dependency structure, see `this blog post
   <https://www.gadom.ski/2022/02/18/dependency-protection-with-python-and-github-actions.html>`_.

If you are building a library that is meant to be imported and used by other
projects, then the correct way to specify dependencies is a little trickier. We
recommended the following setup, if possible:

- Specify direct dependencies with ``>=`` in your setup file (usually
  ``setup.cfg``)
- Keep a ``requirements-min.txt`` file at the top level of your repo with all
  direct dependencies, but this time with ``==`` version specifications
- In CI, test with both a standard install and with ``requirements-min.txt``
- Specify development dependencies with ``~=`` version specifications on the
  MINOR version when appropriate, otherwise ``==``

Examples
^^^^^^^^

Let's say you have a **spam** package that depends on **eggs**, and uses
**milk** and **coffee** as development packages. Your ``setup.cfg`` should
include something like this:

.. code-block:: cfg

   install_requires =
      eggs >= 2.3.4

Then, in your ``requirements-min.txt`` file:

.. code-block::

   eggs == 2.3.4

If you keep your development dependencies in ``requirements-dev.txt``
(recommended), that might look like:

.. code-block::

   milk ~= 5.4
   coffee == 2023.03.16

For an example of this setup in a real-life package, check out `stactools`_.

Tooling
-------

For Python projects, the following linters, formatters, and checkers are
recommended.  Each should be included in requirements file(s) as well as added
as **pre-commit** hooks:

- `mypy`_ for type checking
- `black`_ for formatting
- `ruff`_ for linting
- `pytest`_ for tests
- `doc8`_ for checking :abbr:`rst (reStructuredText)` files

Style
-----

.. warning::

   This style guide is a work in progress

There's quite a few `Python packages in the stac-utils organization
<https://github.com/stac-utils/?q=&type=all&language=python&sort=>`_.  `PySTAC`_
is the "base" repository that includes classes for all the main STAC data
structures (Item, Catalog, and Collection) as well as reading, writing, and
convenience functionality.  Before the creation of this this developer guide, we
had a de facto policy of "do what PySTAC does" for the rest of the
**stac-utils** Python packages. Now, we use this document as the source of
truth.

Using ``datetime``
^^^^^^^^^^^^^^^^^^

Following the lead of the `datetime documentation`_, prefer import the
``datetime`` class (and other classes, e.g. ``timedelta``), and don't rename it:

.. code-block:: python

   # DO
   from datetime import datetime

   # DON't
   import datetime
   import datetime as dt

The exception to this rule is when ``datetime`` is only imported for type checking and
using the class directly interferes with another variable name. In this case, in the
TYPE_CHECKING block you should do ``from datetime import datetime as Datetime``.

.. _PySTAC: https://github.com/stac-utils/pystac
.. _datetime documentation: https://docs.python.org/3/library/datetime.html
.. _mypy: https://www.mypy-lang.org/
.. _black: https://github.com/psf/black
.. _ruff: https://github.com/charliermarsh/ruff
.. _pytest: https://docs.pytest.org/
.. _doc8: https://github.com/pycqa/doc8
.. _pip-tools: https://github.com/jazzband/pip-tools
.. _stactools: https://github.com/stac-utils/stactools
