:original_name: cbr_01_0003.html

.. _cbr_01_0003:

Functions
=========

:ref:`Table 1 <cbr_01_0003__table1414034615119>` lists the basic functions of CBR.

Before using this service, it is recommended that you go to :ref:`basic concepts <cbr_01_0012>` to learn more about CBR, such as about vault and backup policy.

.. _cbr_01_0003__table1414034615119:

.. table:: **Table 1** CBR basic functions

   +---------------------+-------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Category            | Function                            | Description                                                                                                                                                                                 |
   +=====================+=====================================+=============================================================================================================================================================================================+
   | Cloud disk backup   | Backing up disks                    | Cloud disk backup provides snapshot-based data protection for EVS disks. You can use CBR to back up a single disk on a server to protect the data on that disk.                             |
   +---------------------+-------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                     | Policy-driven data backup           | A backup policy allows a vault to automatically execute backup tasks at specified times or intervals. Periodic backups can be used to restore data quickly against data corruption or loss. |
   +---------------------+-------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                     | Backup management                   | When a backup task is running or completed, you can set search criteria to filter backups from the backup list to manage them and view their details.                                       |
   +---------------------+-------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                     | Restoring disk data using backups   | When a disk is faulty or disk data is lost due to misoperations, you can use a backup to restore the disk.                                                                                  |
   +---------------------+-------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                     | Creating disks using backups        | You can use a disk backup to create a disk. After the disk is created, data on the new disk is the same as that in the disk backup.                                                         |
   +---------------------+-------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                     | Sharing backups                     | You can share a server or disk backup with other accounts. Shared backups can be used to create disks or servers.                                                                           |
   +---------------------+-------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Cloud server backup | Backing up servers                  | Cloud server backup uses the consistency snapshot technology for disks to protect data of ECSs. You can use CBR to back up an entire server to protect the data on the server.              |
   +---------------------+-------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                     | Policy-driven data backup           | A backup policy allows a vault to automatically execute backup tasks at specified times or intervals. Periodic backups can be used to restore data quickly against data corruption or loss. |
   +---------------------+-------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                     | Backup management                   | When a backup task is running or completed, you can set search criteria to filter backups from the backup list to manage them and view their details.                                       |
   +---------------------+-------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                     | Restoring server data using backups | When a server is faulty or server data is lost due to misoperations, you can use a backup to restore the server.                                                                            |
   +---------------------+-------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                     | Sharing backups                     | You can share a server or disk backup with other accounts. Shared backups can be used to create disks or servers.                                                                           |
   +---------------------+-------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                     | Creating images using backups       | Cloud server backup allows you to create images using ECS backups. You can use the images to provision ECSs to rapidly restore service running environments.                                |
   +---------------------+-------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
