:original_name: cbr_06_0026.html

.. _cbr_06_0026:

Why Is My Backup Size Larger Than My Disk Size?
===============================================

Symptoms
--------

-  There were files on a server, and the server was backed up. After deleting some files, the server was backed up again. By viewing the used vault capacity, we came to a conclusion that the backup size was not changed or even became bigger.

   For example, a user backed up a server that contains 100 files. The used vault capacity was A. Then the user deleted 10 files and backed up the server again. The used vault capacity changed to B. B may be the same as A or even larger.

-  The ECS backup size is larger than the used disk space obtained from the file system.

Possible Causes
---------------

Possible causes are as follows:

-  The backup mechanism itself causes this problem. The cloud server backups, and cloud disk backups created using CBR are all **block-level backups**. Different from file-level backups, block-level backups are performed by sector (512 bytes) each time.
-  The metadata of the file systems on the disk occupies disk space.
-  To reduce performance overhead, the file system adds a delete marker for the deleted file, but does not erase the data that has been written to the sector, and the metadata on the sector still exists. Block-level backups cannot detect whether data on a sector is deleted or not, but only determine whether a backup needs to be performed by checking whether all data blocks are zero blocks.
-  CBR determines whether data in each sector changes by comparing two snapshots. Data changes include data addition, modification, and deletion. Backup is not performed if there are no data changes. If there are data changes, CBR further checks whether data blocks in the sector are all zero blocks. If so, backup is also not performed. Backups are performed only when there are non-zero blocks. If the data is deleted but metadata in the sector is not, the data block is also recognized as a non-zero block, and backups will be performed.
