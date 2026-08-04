:original_name: cbr_01_0003.html

.. _cbr_01_0003:

Functions
=========

This section describes main functions of CBR. You can check if a certain function is available in a region on the console.

Before using CBR functions, it is recommended that you learn about :ref:`basic CBR concepts <cbr_01_0012>`.

Cloud Disk Backup
-----------------

:ref:`Manual disk backup <cbr_02_0007>`

A cloud disk backup is a snapshot-based backup of EVS disks. You can back up a single disk or all disks to protect data on them.

:ref:`Policy-based backup <cbr_03_0025>`

With a backup policy, you can schedule regular backups of all disks to a vault, enabling fast restoration in case of data loss or corruption.

:ref:`Backup management <cbr_03_0013>`

You can set search criteria to quickly find the backup tasks you want to manage. Then you can view their details, share, restore, or delete them if needed.

:ref:`Disk restoration from backups <cbr_03_0033>`

When a disk is faulty, or its data is lost, you can use a backup to quickly restore the data.

:ref:`Disk creation from backups <cbr_03_0017>`

You can use a disk backup to create a disk that contains the same data as the backup.

:ref:`Sharing a Backup <cbr_03_0014>`

You can share a disk backup with other accounts. Shared backups can be used to create new servers and disks.

Cloud Server Backup
-------------------

:ref:`Manual server backup <cbr_02_0006>`

Cloud server backup uses the consistency snapshot technology to protect data for ECSs without the need to install the Agent on servers. It allows you to back up the entire servers.

:ref:`Policy-based backup <cbr_03_0025>`

With a backup policy, you can schedule regular backups of servers, enabling fast restoration in case of data loss or corruption.

:ref:`Backup management <cbr_03_0013>`

You can set search criteria to quickly find the backup tasks you want to manage. Then you can view their details, share, restore, or delete them if needed.

:ref:`Server restoration from backups <cbr_03_0032>`

When a server is faulty, or its data is lost, you can use a backup to quickly restore the data.

:ref:`Sharing a Backup <cbr_03_0014>`

You can share a server backup with other accounts. Shared backups can be used to create new servers.

:ref:`Image creation from server backups <cbr_03_0016>`

You can create images from ECS backups and then use the images to quickly provision ECSs to restore services.

With cross-region replication, you can replicate backups to destination regions and then create images and use the images to provision ECSs there.
