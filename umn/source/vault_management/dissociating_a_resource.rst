:original_name: cbr_03_0005.html

.. _cbr_03_0005:

Dissociating a Resource
=======================

If you no longer need to back up an associated resource, dissociate it from the vault.

After a resource is dissociated, the backup policy of the vault no longer has any effect on the resource. In addition, all manual and automatic backups of this resource will be deleted. Deleted backups cannot be used for data restoration. Exercise caution when performing this operation.

Dissociating a resource from a vault does not affect the performance of services on the resource.

Procedure
---------

#. Log in to CBR Console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select your region and project.
   c. Choose **Storage** > **Cloud Backup and Recovery**. Select a backup tab from the left navigation pane.

#. On any backup page, locate the target vault and click the vault name.

#. In this example, we will be using the **Cloud Server Backup** page to illustrate the process. Click the **Associated Servers** tab. Find the target server and click **Dissociate** in the **Operation** column. See :ref:`Figure 1 <cbr_03_0005__fig1376320199159>`.

   After a resource is dissociated, the backup or replication policy of the vault no longer has any effect on the resource. In addition, all manual and automatic backups of this resource will be deleted. Deleted backups cannot be used for data restoration. Exercise caution when performing this operation.

   .. _cbr_03_0005__fig1376320199159:

   **Figure 1** Dissociating a server

   |image2|

#. Confirm the information and click **Yes**.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001232186949.png
