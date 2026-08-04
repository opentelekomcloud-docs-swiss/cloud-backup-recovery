:original_name: cbr_02_0004.html

.. _cbr_02_0004:

Creating a Disk Backup Vault
============================

This section describes how to create a disk backup vault.

Procedure
---------

#. Log in to the CBR console.

   a. In the upper left corner, click |image1| and select a region.
   b. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**.

#. In the navigation pane, choose **Cloud Disk Backups**.

#. In the upper right corner of the page, click **Create Disk Backup Vault**.

#. Determine whether to enable backup locking.

   If backup locking is enabled, backups in the vault will not be deleted maliciously or by mistake. This improves data reliability.

   |image3|

   .. important::

      Backup locking cannot be disabled after it is enabled.

#. (Optional) In the disk list, select the disks you want to back up. After disks are selected, they are added to the list of selected disks.


   **Figure 1** Selecting disks

   |image4|

   .. note::

      -  The selected disks must not have been associated with any vault and must be in the **Available** or **In-use** state.
      -  You can also skip this step and associate disks with the vault later.

#. Specify the vault capacity. This capacity is the total space that is required by the disks you want to associate with this vault. Plan the vault capacity and ensure that it is at least as large as the disks you want to back up. If automatic association is enabled and a backup policy is applied to the vault, plan more capacity as required. The capacity ranges from 10 GB to 10,485,760 GB. If automatic capacity expansion is not enabled, the vault capacity will not be automatically expanded, even if the capacity of disks is expanded during use.

   You can expand the vault capacity if it becomes insufficient.


   **Figure 2** Setting the vault capacity

   |image5|

#. Configure auto backup.

   -  If you select **Configure**, you must then select an existing backup policy or create a policy. After the vault is created, CBR will apply the policy to this vault, and all disks associated with this vault will be automatically backed up based on this policy.
   -  If you select **Skip**, disks associated with this vault will not be automatically backed up until you apply a backup policy to the vault.


   **Figure 3** Configuring auto backup

   |image6|

#. (Optional) Configure automatic resource association.

   -  If you select **Configure**, in the next backup period, CBR will automatically scan all unprotected resources, associate them with the vault, and then perform backups.
   -  If you select **Skip**, CBR will not scan and associate unprotected resources with the vault you are creating.

   You can filter unprotected resources by tag. If a tag is selected, only unprotected resources with the specified tag will be associated with the vault. Or, all unprotected resources will be associated.

   If no tag is available, you can create tags on the corresponding resource page. You can search for vaults by specifying a maximum of 5 tags at a time. If you select more than one tag, the vaults with any of the specified tags will be returned.

#. (Optional) Add tags to the vault.

   Tags are key-value pairs, which are used to identify, classify, and search for vaults. Vault tags are only used to filter and manage vaults. A vault can have a maximum of 20 tags.

   :ref:`Table 1 <cbr_02_0004__cbr_02_0003_table191162312815>` describes the parameters of a tag.

   .. _cbr_02_0004__cbr_02_0003_table191162312815:

   .. table:: **Table 1** Tag parameter description

      +-----------------------+------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                            | Example Value         |
      +=======================+========================================================================+=======================+
      | Key                   | Each tag has a unique key. You can enter a custom key.                 | Key_0001              |
      |                       |                                                                        |                       |
      |                       | A tag key:                                                             |                       |
      |                       |                                                                        |                       |
      |                       | -  Can contain 1 to 36 Unicode characters.                             |                       |
      |                       | -  Can contain only letters, digits, hyphens (-), and underscores (_). |                       |
      +-----------------------+------------------------------------------------------------------------+-----------------------+
      | Value                 | A tag value can be repetitive or left blank.                           | Value_0001            |
      |                       |                                                                        |                       |
      |                       | A tag value:                                                           |                       |
      |                       |                                                                        |                       |
      |                       | -  Can contain 0 to 43 Unicode characters.                             |                       |
      |                       | -  Can contain only letters, digits, hyphens (-), and underscores (_). |                       |
      +-----------------------+------------------------------------------------------------------------+-----------------------+

#. Specify a name for the vault.

   The name can contain 1 to 64 characters. Only letters, digits, underscores (_), and hyphens (-) are allowed. Example: **vault-612c**.


   .. figure:: /_static/images/en-us_image_0251456277.png
      :alt: **Figure 4** Setting the vault name

      **Figure 4** Setting the vault name

   .. note::

      You can also use the default name **vault\_**\ *xxxx*.

#. Complete the creation as prompted.

#. Go back to the **Cloud Disk Backups** page. You can see the created vault in the vault list.

   You can associate disks with the new vault or create backup for the disks. For details, see :ref:`Vault Management <cbr_03_0002>`.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image3| image:: /_static/images/en-us_image_0000002124587690.png
.. |image4| image:: /_static/images/en-us_image_0000002021491294.png
.. |image5| image:: /_static/images/en-us_image_0000001186235530.png
.. |image6| image:: /_static/images/en-us_image_0000001231755471.png
