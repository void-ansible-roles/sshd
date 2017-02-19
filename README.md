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
  * sshd_usepam: true
  * sshd_Ciphers:
      - chacha20-poly1305@openssh.com
      - aes256-gcm@openssh.com
      - aes256-ctr
  * sshd_KexAlgorithms:
      - curve25519-sha256@libssh.org
      - diffie-hellman-group-exchange-sha256
  * sshd_MACs:
      - hmac-sha2-512-etm@openssh.com
      - hmac-sha2-512,hmac-sha2-256
      - hmac-ripemd160
  * sshd_AuthenticationMethods:
      - publickey

Variables Required:
  * None

Optional Variables:
  * sshd_banner: Name of a file to copy as the sshd banner
  * sshd_listen_addresses: List of addresses to run sshd on.  If this variable is not present, sshd will bind to all addresses on the system.
  * sshd_usepam: binary, whether or not to use PAM challenge/response
  * sshd_Ciphers: List of ciphers to use
  * sshd_KexAlgorithms: List of Key Exchange Algorithms to use
  * sshd_MACs: List of Message Authentication Codes to use
  * sshd_AllowGroupAlways: group which will always be added to the AllowedGroups list
  * sshd_AllowGroups: list of groups which will be added with AllowGroups entries
  * sshd_AuthenticationMethods:  List of authentication methods to try
  * sshd_AuthorizedKeysCommand: Optional command to run to retrieve keys

Files Required:
  * None

Optional Files:
  * ssh_banners: Files containing ssh banners, it is suggested that these files are ascii art banners not larger than 24 lines long and 80 columns wide.  These files must be accessible to ansible, so it is suggested to store them within the directory tree which contains the rest of the ansible files.

Conflicting Roles:
  * None

Depends On:
  * None
