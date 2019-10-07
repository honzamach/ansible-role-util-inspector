.. _section-role-util-inspector:

Role **util_inspector**
================================================================================

Ansible role for inspecting target systems and generating documentation.

* `Ansible Galaxy page <https://galaxy.ansible.com/honzamach/util_inspector>`__
* `GitHub repository <https://github.com/honzamach/ansible-role-util_inspector>`__
* `Travis CI page <https://travis-ci.org/honzamach/ansible-role-util_inspector>`__


Requirements
--------------------------------------------------------------------------------

Python2 with pip utility and Python3 with pip3 utility should already be installed
on target system.


Role Variables
--------------------------------------------------------------------------------

There are following internal role variables defined in ``defaults/main.yml`` file,
that can be overriden and adjusted as needed:

:envvar:`hm_util_inspector__docs_dir`
	Name of the directory to which to generate the documentation.

	*Type:* ``string`` | *Default:* ``"vault/docs"``


Usage and customization
--------------------------------------------------------------------------------

This role is (attempted to be) written according to the `Ansible best practices <https://docs.ansible.com/ansible/latest/user_guide/playbooks_best_practices.html>`__. The default implementation should fit most users,
however you may customize it by tweaking default variables and providing custom
templates.


Variable customizations
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Most of the usefull variables are defined in ``defaults/main.yml`` file, so they
can be easily overridden almost from `anywhere <https://docs.ansible.com/ansible/latest/user_guide/playbooks_variables.html#variable-precedence-where-should-i-put-a-variable>`__.


Template customizations
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This roles uses *with_first_found* mechanism for all of its templates. If you do
not like anything about built-in template files you may provide your own custom
templates. For now please see the role tasks for list of all checked paths for
each of the template files.


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


Example Playbook
--------------------------------------------------------------------------------

Example content of inventory file ``inventory``::

    [servers]
    localhost

Example content of role playbook file ``playbook.yml``::

    - hosts: servers
      remote_user: root
      roles:
        - role: honzamach.util_inspector
      tags:
        - role-util-inspector

Example usage::

    ansible-playbook -i inventory playbook.yml


License
--------------------------------------------------------------------------------

MIT


Author Information
--------------------------------------------------------------------------------

Jan Mach <honza.mach.ml@gmail.com>
