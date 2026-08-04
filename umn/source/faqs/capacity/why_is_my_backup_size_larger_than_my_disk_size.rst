:original_name: cbr_06_0026.html

.. _cbr_06_0026:

Why Is My Backup Size Larger Than My Disk Size?
===============================================

Symptoms
--------

-  There were files on a server, and the server was backed up. After deleting some files, the server was backed up again. By viewing the used vault capacity, we came to a conclusion that the backup size was not changed or even became bigger.

   For example, a user backed up a server containing 100 files, resulting in a used vault capacity of A. After deleting 10 files and running another backup, the used vault capacity became B. B may be the same as A or even larger.

-  The ECS backup size is larger than the used disk space obtained from the file system.

Possible Causes
---------------

Possible causes are as follows:

-  File system deletion: When a file is deleted from the operating system, the disk blocks it occupied are only marked as free space. The underlying data is not erased, so block-level backups still include this data.
-  File system metadata overhead: File system management information (such as permissions and directory structures) occupies space. Although such information is not counted in the file size, it must still be backed up.
-  Disk storage allocation: Disks are allocated in clusters, which can cause internal fragments when storing small files. In addition, hidden files (like hibernation files) also occupy physical space. As a result, the backup size may be larger than the size reported by the file system.
-  Block-level backup: The backup size is calculated by summing all non-empty blocks, based on the disk's fixed block size. If file data is scattered across the disk, more blocks are marked non-empty, increasing backup size. (Disk-level backups in the industry are typically larger than the size reported by the file system.)
