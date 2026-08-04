:original_name: cbr_06_0007.html

.. _cbr_06_0007:

Do I Need to Stop the Server Before Performing a Backup?
========================================================

No. You can back up servers that are in use.

When a server is running, data is written to the disks, and some newly generated data is temporarily cached in the server's memory. During a backup task, data in the memory will not be automatically written into disks, so the disk data and their backups may be inconsistent.

To ensure data integrity, you are advised to run backups during off-peak hours, preferably in the early morning, when the disks are not receiving write operations.
