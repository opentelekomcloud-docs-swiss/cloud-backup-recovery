:original_name: cbr_03_0116.html

.. _cbr_03_0116:

Migrating a Resource
====================

Migrating a resource means that you dissociate a resource from a vault and then associate it to another vault. All backups of the resource will be migrated to the destination vault.

Constraints
-----------

-  Resources can be migrated only when the source and destination vaults are in the **Available** or **Locked** state.
-  The source and destination vaults for resource migration must be of the same specifications.
-  The remaining capacity of the destination vault must be greater than the size of resource backups to be migrated.
-  Cross-account resource migration is currently not supported.
-  The source and destination vaults must be in the same region.

Procedure
---------

#. Log in to the CBR console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select a region.
   c. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**. Select a backup type from the left navigation pane.

#. Find the target vault and click its name. In this example, we will be using the **Cloud Server Backups** page to illustrate the process.

#. Click the **Associated Servers** tab. Find the target server and click **Migrate** in the **Operation** column.


   .. figure:: /_static/images/en-us_image_0000001628917242.png
      :alt: **Figure 1** Migrating a resource

      **Figure 1** Migrating a resource

#. Select the destination vault and click **OK**.

#. View the migration progress on the **Tasks** page. If **Status** changes to **Successful**, the resource has been migrated.

#. Go to the destination vault to confirm that the resource has been associated and all its backups have been migrated.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
