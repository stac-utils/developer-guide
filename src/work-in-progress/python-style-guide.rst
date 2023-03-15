Python style guide
==================

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
------------------

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
