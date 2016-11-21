sshd
====


What is does this role do?
--------------------------

This role configures sshd for use on a Void Linux system.  This role handles tasks such as security hardening and making sure that sshd is only running on the addresses expected.


Meta
----

Files Managed:
  * /etc/ssh/sshd_config

Defaults Provided:
  * sshd_banner: ssh_banner_default

Variables Required:
  * None

Optional Variables:
  * sshd_banner: Name of a file to copy as the sshd banner
  * sshd_listen_addresses: List of addresses to run sshd on.  If this variable is not present, sshd will bind to all addresses on the system.

Files Required:
  * None

Optional Files:
  * ssh_banners: Files containing ssh banners, it is suggested that these files are ascii art banners not larger than 24 lines long and 80 columns wide.  These files must be accessible to ansible, so it is suggested to store them within the directory tree which contains the rest of the ansible files.

Conflicting Roles:
  * None

Depends On:
  * None
