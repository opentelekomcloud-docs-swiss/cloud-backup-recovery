:original_name: cbr_01_0002.html

.. _cbr_01_0002:

What Is CBR?
============

Overview
--------

Cloud Backup and Recovery (CBR) enables you to back up Elastic Cloud Servers (ECSs) and Elastic Volume Service (EVS) disks with ease. In case of a virus attack, accidental deletion, or software or hardware fault, you can restore data to any point in the past when the data was backed up.

CBR protects your services by ensuring the security and consistency of your data.

Product Architecture
--------------------

CBR consists of backups, vaults, and policies.

**Backup**

A backup is a copy of a particular chunk of data and is usually stored elsewhere so that it may be used to restore the original data in the event of data loss. The following are the types of CBR backups:

-  Cloud disk backup. This type of backup provides snapshot-based data protection for EVS disks.
-  Cloud server backup. This type of backup uses the consistency snapshot technology for disks to protect data of ECSs.

**Vault**

CBR uses vaults to store backups. Before creating a backup, you need to create at least one vault and associate the resource you want to back up with the vault. Then the generated resource backups are stored in the associated vault.

The backups of different types of resources must be stored in different types of vaults.

**Policy**

-  Backup policies: To perform automatic backups, configure a backup policy by setting the execution times of backup tasks, the backup frequency, and retention rules, and then apply the policy to a vault.


**Figure 1** Architecture of CBR

|image1|

Differences Between Backup Types
--------------------------------

.. table:: **Table 1** Differences between backup types

   +-------------------------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
   | Item                          | Cloud Server Backup                                                              | Cloud Disk Backup                                                                                       |
   +===============================+==================================================================================+=========================================================================================================+
   | Backup and restoration object | All disks (system and data disks) on a server                                    | One or more specified disks (system or data disks)                                                      |
   +-------------------------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
   | Recommended scenario          | An entire cloud server needs to be protected.                                    | Only data disks need to be backed up, because the system disk does not contain users' application data. |
   +-------------------------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
   | Advantages                    | All disks on a server are backed up at the same time, ensuring data consistency. | Backup cost is reduced without compromising data security.                                              |
   +-------------------------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+

Backup Mechanism
----------------

CBR in-cloud backups offer block-level backup. A full backup is performed only for the first backup and backs up all used data blocks. For example, if the size of a disk is 100 GB and the used space is 40 GB, the 40 GB of data is backed up. An incremental backup backs up only the data changed since the last backup, which is storage- and time-efficient. When a backup is deleted, only the data blocks that are not depended on by other backups are deleted, so that other backups can still be used for restoration. Both a full backup and an incremental backup can restore data to the state at a given backup point in time.

When creating a backup of a disk, CBR also creates a snapshot for it. Every time a new disk backup is created, CBR deletes the old snapshot and keeps only the latest snapshot.

CBR stores backup data in OBS, enhancing backup data security.

Backup Options
--------------

CBR supports one-off backup and periodic backup. A one-off backup task is manually created by users and is executed only once. Periodic backup tasks are automatically executed based on a user-defined backup policy.

:ref:`Table 2 <cbr_01_0002__table31963779194543>` describes the two backup options.

.. _cbr_01_0002__table31963779194543:

.. table:: **Table 2** One-off backup and periodic backup

   +------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------+
   | Item                   | One-Off Backup                                                                                                                                                                                         | Periodic Backup                                                                                                                             |
   +========================+========================================================================================================================================================================================================+=============================================================================================================================================+
   | Backup policy          | Not required                                                                                                                                                                                           | Required                                                                                                                                    |
   +------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------+
   | Number of backup tasks | One manual backup task                                                                                                                                                                                 | Periodic tasks driven by a backup policy                                                                                                    |
   +------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------+
   | Backup name            | User-defined backup name, which is **manualbk\_**\ *xxxx* by default                                                                                                                                   | System-assigned backup name, which is **autobk\_**\ *xxxx* by default                                                                       |
   +------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------+
   | Backup mode            | Full backup for the first time and incremental backup subsequently, by default                                                                                                                         | Full backup for the first time and incremental backup subsequently, by default                                                              |
   +------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------+
   | Application scenario   | Executed before patching or upgrading the OS or upgrading an application on a resource. A one-off backup can be used to restore the resource to the original state if the patching or upgrading fails. | Executed for routine maintenance of a resource. The latest backup can be used for restoration if an unexpected failure or data loss occurs. |
   +------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------+

You can also use the two backup options together if needed. For example, you can associate all servers with a vault and then apply a backup policy to the vault to execute periodic backup for all the resources in the vault. Additionally, you can perform backup for the most important servers on demand to enhance data security. :ref:`Figure 2 <cbr_01_0002__fig190314191275>` shows the intermixed use of the two backup options.

.. _cbr_01_0002__fig190314191275:

.. figure:: /_static/images/en-us_image_0285742235.png
   :alt: **Figure 2** Intermixed use of the two backup options

   **Figure 2** Intermixed use of the two backup options

Method of Access
----------------

You can access the CBR service through the management console or by calling HTTPS-based APIs.

-  Management Console

   The console is a web-based UI where you can perform operations on CBR resources easily. Log in to the management console and choose **Cloud Backup and Recovery**.

-  Calling APIs

   If you need to integrate the CBR service into a third-party system for secondary development, use APIs to access the CBR service. For details, see the *Cloud Backup and Recovery API Reference*.

.. |image1| image:: /_static/images/en-us_image_0242743738.png
