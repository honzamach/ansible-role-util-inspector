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

:envvar:`rs_pgsql__user`
	Name of the UNIX system user for PostgreSQL database.

	*Type:* ``string`` | *Default:* ``"postgres"``

:envvar:`rs_pgsql__group`
	Name of the UNIX system group for PostgreSQL database.

	*Type:* ``string`` | *Default:* ``"postgres"``

:envvar:`rs_pgsql__logdir`
	Path to log file.

	*Type:* ``string`` | *Default:* ``"/var/log/postgresql"``

:envvar:`rs_pgsql__logrotate`
	Log rotation switch (true/false).

	*Type:* ``bool`` | *Default:* ``true``

:envvar:`rs_pgsql__logrotate_options`
	Log rotation options.

	*Type:* ``list of strings``

There are following internal Debian specific role variables defined in ``vars/debian.yml``
file, that can be overriden and adjusted as needed:

:envvar:`rs_pgsql__apt_key_url`
	URL leading to GPG key for signing deb packages

	*Type:* ``string`` | *Default:* ``"https://www.postgresql.org/media/keys/ACCC4CF8.asc"``

:envvar:`rs_pgsql__apt_key_id`
	Identifier of the signing key.

	*Type:* ``string`` | *Default:* ``"ACCC4CF8"``

:envvar:`rs_pgsql__apt_repository`
	Location of PostgreSQL repository.

	*Type:* ``string`` | *Default:* ``"deb http://apt.postgresql.org/pub/repos/apt/ {{ ansible_lsb['codename'] }}-pgdg main"``

:envvar:`rs_pgsql__service_name`
	Name of the PostgreSQL service.

	*Type:* ``string`` | *Default:* ``"postgresql"``

Additionally this role makes use of following built-in Ansible variables:

:envvar:`ansible_lsb['codename']`
	Debian distribution codename is used to generate correct APT repository URL.


Managed files
--------------------------------------------------------------------------------

This role directly manages content of following files on target system:

* ``/etc/logrotate.d/postgresql-common``


Dependencies
--------------------------------------------------------------------------------

This role is not dependent on any other role.

Following roles have direct dependency on this role:

* :ref:`app-mentat <section-role-app-mentat>`


Example Playbook
--------------------------------------------------------------------------------

Example content of inventory file ``inventory``::

	[servers-svc-postgresql]
	localhost

Example content of role playbook file ``playbook.yml``::

	- hosts: servers-svc-postgresql
	  remote_user: root
	  roles:
	    - role: svc-postgresql
	  tags:
	    - role-application
	    - svc-postgresql

Example usage::

	ansible-playbook -i inventory playbook.yml


License
--------------------------------------------------------------------------------

MIT


Author Information
--------------------------------------------------------------------------------

Jan Mach <jan.mach@cesnet.cz>, CESNET, a.l.e.
