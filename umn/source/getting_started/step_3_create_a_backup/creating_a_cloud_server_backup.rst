:original_name: cbr_02_0006.html

.. _cbr_02_0006:

Creating a Cloud Server Backup
==============================

This section describes how to quickly create a cloud server backup.

If you do not need an ECS for the moment, you can back up the ECS and then delete it. When you want the ECS later, you can create an image from the ECS backup and use the image to create the ECS.

Backing up a server does not impact the server performance.

The backup service experiences peak usage from 22:00 to 08:00, during which delays may occur. To ensure optimal performance, it is recommended that you evaluate your service types and stagger backups across discrete time periods.

Prerequisites
-------------

-  Only servers in the **Running** or **Stopped** state can be backed up.
-  At least one server backup vault is available.

Procedure
---------

#. Log in to the CBR console.

   a. In the upper left corner, click |image1| and select a region.
   b. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**.

#. On the **Cloud Server Backups** page, click the **Vaults** tab and find the vault with which the server is associated.

#. Perform backup in either of the following ways:

   -  Click **Perform Backup** in the **Operation** column. In the server list, select the server you want to back up. After a server is selected, it is added to the list of selected servers.


      **Figure 1** Selecting the server to be backed up

      |image3|

   -  Click the vault name to go to the vault details page. On the **Associated Servers** tab, locate the target server and click **Perform Backup** in the **Operation** column.


      **Figure 2** Perform Backup

      |image4|

#. Set **Name** and **Description** for the backup.

   .. table:: **Table 1** Parameter description

      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                                 | Remarks               |
      +=======================+=============================================================================================================================================================+=======================+
      | Name                  | Name of the backup you are creating.                                                                                                                        | manualbk_d819         |
      |                       |                                                                                                                                                             |                       |
      |                       | The name can contain 1 to 64 characters. Only letters, digits, underscores (_), and hyphens (-) are allowed.                                                |                       |
      |                       |                                                                                                                                                             |                       |
      |                       | .. note::                                                                                                                                                   |                       |
      |                       |                                                                                                                                                             |                       |
      |                       |    You can also use the default name **manualbk\_**\ *xxxx*.                                                                                                |                       |
      |                       |                                                                                                                                                             |                       |
      |                       |    If multiple servers are to be backed up, the system automatically adds suffixes to their backup names, for example, **backup-0001** and **backup-0002**. |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description           | Description of the backup.                                                                                                                                  | --                    |
      |                       |                                                                                                                                                             |                       |
      |                       | It cannot exceed 255 characters.                                                                                                                            |                       |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. Choose whether to enable full backup. If full backup is enabled, CBR performs a full backup on every associated server. A full backup requires a larger capacity than an incremental backup.


   **Figure 3** Full Backup

   |image5|

#. Click **OK**. CBR automatically creates a backup for the server.

   On the **Backups** tab, if the status of the backup is **Available**, the backup task is successful.

   .. note::

      -  A server can be restarted if the backup progress exceeds 10%. However, to ensure data integrity, restart it after the backup is complete.

   After the backup is complete, you can use the backup to restore server data or create an image. For details, see :ref:`Restoring from a Cloud Server Backup <cbr_03_0032>` and :ref:`Creating an Image from a Cloud Server Backup <cbr_03_0016>`.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image3| image:: /_static/images/en-us_image_0000002026445662.png
.. |image4| image:: /_static/images/en-us_image_0000002062644745.png
.. |image5| image:: /_static/images/en-us_image_0184043658.png
