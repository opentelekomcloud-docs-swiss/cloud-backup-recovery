:original_name: cbr_06_0054.html

.. _cbr_06_0054:

What Are the Differences Between Cloud Server Backup and Cloud Disk Backup?
===========================================================================

:ref:`Table 1 <cbr_06_0054__table1965919985417>` describes the differences between cloud server backup and cloud disk backup.

.. _cbr_06_0054__table1965919985417:

.. table:: **Table 1** Differences between cloud server backup and cloud disk backup

   +---------------------------------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
   | Item                                  | Cloud Server Backup                                                              | Cloud Disk Backup                                                                                       |
   +=======================================+==================================================================================+=========================================================================================================+
   | Resources to be backed up or restored | All disks (system disks and data disks) or some disks on a server                | One or more specified disks (system or data disks)                                                      |
   +---------------------------------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
   | Recommended scenario                  | An entire cloud server needs to be protected.                                    | Only data disks need to be backed up, because the system disk does not contain users' application data. |
   +---------------------------------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
   | Advantages                            | All disks on a server are backed up at the same time, ensuring data consistency. | Backup cost is reduced without compromising data security.                                              |
   +---------------------------------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------+
