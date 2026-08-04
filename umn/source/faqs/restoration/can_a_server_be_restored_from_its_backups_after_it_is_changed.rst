:original_name: cbr_06_0016.html

.. _cbr_06_0016:

Can a Server Be Restored from Its Backups After It Is Changed?
==============================================================

Yes. If a server has been backed up and later modified (for example, by adding, deleting, or expanding disks), its existing backups can still be used to restore data. However, it is recommended that you perform another backup after making such changes.

If you add a disk after a backup, restoring data from that backup will not restore any data stored on the newly added disk.

If you delete a disk after a backup and then restore data from that backup, the data on the deleted disk will not be restored.
