:original_name: cbr_03_0116.html

.. _cbr_03_0116:

Migrating Resources from a Vault
================================

Vault resources can be migrated when service requirements change and the existing vault no longer meets the new scale or specifications.

Migrating a resource means that you dissociate the resource from a vault and then associate it with another vault. All backups of the resource will be migrated to the destination vault.

Constraints
-----------

-  Resources can be migrated only when the source and destination vaults are in the **Available** or **Locked** state.
-  Resources can be migrated only when no task is being executed in the source and destination vaults.
-  The remaining capacity of the destination vault must be greater than the size of the resource backups to be migrated.
-  Cross-account resource migration is currently not supported.
-  The source and destination vaults must be in the same region.
-  The source and destination vaults must be of the same type. For example, resources in a server backup vault can be migrated to another server backup vault, but cannot be migrated to another disk backup vault.

Procedure
---------

#. Log in to the CBR console.

   a. In the upper left corner, click |image1| and select a region.
   b. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**.

#. On a required backup page, locate the vault where the target resource is associated and click its name.

#. Click the **Associated Servers** tab. Find the target server and click **Migrate** in the **Operation** column.


   .. figure:: /_static/images/en-us_image_0000002021313754.png
      :alt: **Figure 1** Migrating a resource

      **Figure 1** Migrating a resource

#. Select the destination vault and click **OK**.

#. View the migration progress on the **Tasks** page. If **Status** changes to **Successful**, the resource has been migrated.

#. Go to the destination vault to confirm that the resource has been associated and all its backups have been migrated.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
