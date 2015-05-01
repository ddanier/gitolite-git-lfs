gitolite-git-lfs
================

This is a proof of concept git-lfs storage server helper for gitolite.

It has been written to work well with django-git-lfs, see:
https://github.com/ddanier/django-git-lfs

Requirements
------------

* Gitolite
* Perl: JSON and LWP (HTTP)

Install
-------

1. Setup LOCAL_CODE in gitolite.
2. Add LFS_URL to .gitolite.rc, for example after LOCAL_CODE. This should point to the perms-view
   of django-git-lfs for example.
3. Add LFS_TOKEN to .gitolite.rc, for example after LOCAL_CODE. This is a secret value used to
   grant access to the server.
   (See django-git-lfs's settings.LFS_PERMS_TOKEN for reference)
4. Put git-lfs-authenticate into $LOCAL_CODE/commands/
5. Run 'gitolite setup'

TODO
----

More secure authentication between git-lfs-authenticate and Git LFS server. A secure token should
be generated using some cryptographical hash method.
