.. _section-role-util-inspector:

Role **util_inspector**
================================================================================

.. note::

    This documentation page and role itself is still work in progress.

* `Ansible Galaxy page <https://galaxy.ansible.com/honzamach/util_inspector>`__
* `GitHub repository <https://github.com/honzamach/ansible-role-util_inspector>`__
* `Travis CI page <https://travis-ci.org/honzamach/ansible-role-util_inspector>`__

Ansible role for inspecting target systems and generating inventory documentation.

Currently following documentation sections are generated:

* **Inventory** - Overview of all your managed servers with most important parameters
  displayed neatly in table and with links to server detail pages.
* **Users** - Overview of all your users with links to user detail pages.
* ** Monitoring** - Overview of monitoring setup of your servers.

**Table of Contents:**

* :ref:`section-role-timesynced-installation`
* :ref:`section-role-timesynced-usage`
* :ref:`section-role-timesynced-variables`
* :ref:`section-role-timesynced-author`

This role is part of the `MSMS <https://github.com/honzamach/msms>`__ package.
Some common features are documented in its :ref:`manual <section-manual>`.


.. _section-role-util-inspector-installation:

Installation
--------------------------------------------------------------------------------

To install the role `honzamach.util_inspector <https://galaxy.ansible.com/honzamach/util_inspector>`__
from `Ansible Galaxy <https://galaxy.ansible.com/>`__ please use variation of
following command::

    ansible-galaxy install honzamach.util_inspector

To install the role directly from `GitHub <https://github.com>`__ by cloning the
`ansible-role-util-inspector <https://github.com/honzamach/ansible-role-util-inspector>`__
repository please use variation of following command::

    git clone https://github.com/honzamach/ansible-role-util-inspector.git honzamach.util_inspector

Currently the advantage of using direct Git cloning is the ability to easily update
the role when new version comes out.


.. _section-role-util-inspector-usage:

Usage
--------------------------------------------------------------------------------

Use attached role playbook file ``role_util_inspector.yml``, there is no need
for customizations.

Example usage::

    # Run everything:
    ansible-playbook --ask-vault-pass --inventory inventory role_util_inspector.yml


.. _section-role-util-inspector-variables:

Configuration variables
--------------------------------------------------------------------------------


Internal role variables
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. envvar:: hm_util_inspector__docs_dir

	Name of the directory to which to generate the documentation.

    * *Datatype:* ``string``
    * *Default:* ``"inventory/docs"``

.. envvar:: hm_util_inspector__groups_to_roles

	Mapping of group names to roles. This feature is used when generating server
	inventory detail page to provide links directly to roles, that are being applied
	to particular server.

	* *Datatype:* ``dictionary``
    * *Default:* (please see file ``defaults/main.yml`` for details)


.. _section-role-util-inspector-author:

Author and license
--------------------------------------------------------------------------------

| *Copyright:* (C) since 2019 Honza Mach <honza.mach.ml@gmail.com>
| *Author:* Honza Mach <honza.mach.ml@gmail.com>
| Use of this role is governed by the MIT license, see LICENSE file.
|
