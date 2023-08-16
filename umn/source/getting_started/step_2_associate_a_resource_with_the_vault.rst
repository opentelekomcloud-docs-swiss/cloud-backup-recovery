:original_name: cbr_02_0009.html

.. _cbr_02_0009:

Step 2: Associate a Resource with the Vault
===========================================

If you have already associated servers or disks when creating a vault, skip this step.

After a server backup vault or disk backup vault is created, you can associate servers or disks with the vault to back up these resources.

Prerequisites
-------------

-  The servers you plan to associate with a vault must be in the **Running** or **Stopped** state.
-  The disks you plan to associate with a vault must be in the **Available** or **In-use** state.
-  The servers you plan to associate with a vault must have at least one disk attached.
-  The vault and the resources to be associated must be in the same region.
-  The total capacity of the resources to be associated cannot be greater than the capacity of the vault.

Procedure
---------

#. Log in to CBR Console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select your region and project.
   c. Choose **Storage** > **Cloud Backup and Recovery**. Select a backup tab from the left navigation pane.

#. On a backup page, locate the target vault and click **Associate Server**, **Associate Disk**.

#. In the resource list, select the resources you want to associate with the vault. After resources are selected, they are added to the list of selected resources. See :ref:`Figure 1 <cbr_02_0009__fig20466879539>`.

   .. _cbr_02_0009__fig20466879539:

   **Figure 1** Associate Server

   |image2|

#. Click **OK**. Then in the **Associated Servers** column in the vault list, you can view the number of resources that have been successfully associated.

   .. note::

      If a new disk is attached to an associated server, the system automatically identifies the new disk and includes the new disk in subsequent backup tasks.

Automatic Association
---------------------

Backup vaults support automatic association with resources that are not backed up. After successful association, resources will be backed up according to the backup policy applied to the vault.

-  You can enable automatic association only when the vault's remaining capacity is greater than 40 GB. Remaining capacity of a vault = Total capacity of the vault - Capacity of resources associated with the vault. You can obtain the vault capacity and associated capacity in the **Basic Information** area on the details page of the vault. Specifically, if the capacity of a server backup vault is 800 GB and it has been associated with two 100 GB servers, the remaining capacity is 600 GB (800 GB - 200 GB). In this case, you can enable automatic association.
-  If multiple vaults are enabled with automatic association, the system scans their backup policies and associates resources with the vault whose next scheduled backup time is the earliest.
-  When the capacity of the vault selected by the system is used up, resources will be associated with the vault whose next scheduled backup time is the second earliest.
-  If a backup policy with the earliest scheduled backup time is applied to more than one vault, the system randomly associates the resources with one of these vaults.
-  If a vault is enabled with automatic association but no backup policy has been applied to it, no resources will be automatically associated with this vault. You can manually associate resources that have not been backed up with the vault.
-  After the automatic association function is disabled for a vault, the vault stops automatically scanning for resources that have not been backed up. The associated resources are not affected.

#. Log in to CBR Console.

   a. Log in to the management console.
   b. Click |image3| in the upper left corner and select your region and project.
   c. Choose **Storage** > **Cloud Backup and Recovery**.

#. On any backup page, locate the target vault.

#. Choose **More** > **Enable Automatic Association** in the **Operation** column of the vault.

   You can add tags to filter the servers to be associated. If tags are added, only the vaults with the specified tags will be associated.

#. After the function is enabled, you can see **Automatic association** in the **Associated Servers** column of the vault list.

#. (Optional) If the automatic association function is not required, choose **More** > **Disable Automatic Association** in the **Operation** column of the vault.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001232200087.png
.. |image3| image:: /_static/images/en-us_image_0160754270.png
