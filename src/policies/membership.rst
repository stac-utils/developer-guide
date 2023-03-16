Membership
==========

.. admonition:: Proposal

    This document is a description of the current ad-hoc process, and has not
    been formally approved.

Repository level permissions
----------------------------

As a rule, Github users that need elevated permissions on **stac-utils**
repositories should be given those permissions on the repositories themselves,
not the whole organization. Users who have demonstrated good knowledge of the
code base, usually via multiple contributions, may be given ``write``
permissions, which allow for the approval and merging of pull requests.
Any permissions above ``write`` should be reserved for members or owners of the
organization.

.. _members:

Members
-------

From the `Github documentation
<https://docs.github.com/en/organizations/managing-peoples-access-to-your-organization-with-roles/roles-in-an-organization#organization-members>`__:

    The default, non-administrative role for people in an organization is the
    organization member. By default, organization members have a number of
    permissions, including the ability to create repositories and project
    boards.

The current public members of the **stac-utils** repository are viewable on Github
via `this page <https://github.com/orgs/stac-utils/people?query=role%3Amember>`__.
Members should be contributors from the community that create new repositories.
To become a member, users should contact a current owner with a rationale for
their inclusion as a member. If the user is only expected to create one new
repository, it may be better to simply transfer that repository to the
organization (often done by transferring the repository to a owner first, then
to the organization), rather than add the person as a member.

.. _owners:

Owners
------

From the `Github documentation
<https://docs.github.com/en/organizations/managing-peoples-access-to-your-organization-with-roles/roles-in-an-organization#organization-owners>`__:

    Organization owners have complete administrative access to your
    organization. This role should be limited, but to no less than two people,
    in your organization.

The current public owners of the **stac-utils** repository are viewable on Github
via `this page <https://github.com/orgs/stac-utils/people?query=role%3Aowner>`__.
New owners may be added if they are doing significant work in the **stac-utils**
organization and need those owner permissions to continue that work.

To request owner permissions, a current member should send a request to
a current owner with a written justification of why the elevated permissions
are needed.

Removing users
--------------

We do not currently have a policy or procedure around removing users or
downgrading user permissions.
