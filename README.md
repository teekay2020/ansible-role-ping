ansible-role-ping
=========

This is a wrapper around ping and win_ping for use in playbooks. It can be used instead of ansible -m ping or ansible -m win_ping. It has the advantage of being able to use the group_vars from the playbook so you can set the winrm settings and also figures out if it windows or linux and runs the right command.


Role Variables
--------------

The group_vars needs to be configured appropriately for windows hosts

e.g

	ansible_user: username
	ansible_password: "{{ username_winrm_password }}"
	ansible_port: 5986
	ansible_connection: winrm
	# The following is necessary for Python 2.7.9+ (or any older Python that has backported SSLContext, eg, Python 2.7.5 on RHEL7) when using default WinRM self-signed certificates:
	ansible_winrm_server_cert_validation: ignore


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: all
      roles:
         - { role: ansible-role-ping }


.
------------------
.
