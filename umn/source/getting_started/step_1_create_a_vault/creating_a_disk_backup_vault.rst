:original_name: cbr_02_0004.html

.. _cbr_02_0004:

Creating a Disk Backup Vault
============================

This section describes how to create a disk backup vault.

Procedure
---------

#. Log in to the CBR console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select a region.
   c. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**. Select a backup type from the left navigation pane.

#. In the upper right corner of the page, click **Create Disk Backup Vault**.

#. Determine whether to enable backup locking .

   If backup locking is enabled, backups in the vault will not be deleted maliciously or by mistake. This improves data reliability.

   |image3|

   .. important::

      Backup locking cannot be disabled after it is enabled.

#. (Optional) In the disk list, select the disks you want to back up. After disks are selected, they are added to the list of selected disks. See :ref:`Figure 1 <cbr_02_0004__fig204531717131710>`.

   .. _cbr_02_0004__fig204531717131710:

   **Figure 1** Selecting disks

   |image4|

   .. note::

      -  The selected disks must have not been associated with any vault and must be in the **Available** or **In-use** state.
      -  You can also associate disks with the vault you are creating later if you skip this step.

#. Specify a vault capacity ranging from 10 GB to 10,485,760 GB. Properly plan the vault capacity, which must be at least the same as the size of the disks you want to back up.


   **Figure 2** Setting the vault capacity

   |image5|

#. Configure auto backup. See :ref:`Figure 3 <cbr_02_0004__fig4582143195315>`.

   -  If you select **Configure**, you must then select an existing backup policy or create a new policy. After the vault is created, CBR will apply the policy to this vault, and all disks associated with this vault will be automatically backed up based on this policy.
   -  If you select **Skip**, disks associated with this vault will not be automatically backed up until you apply a backup policy to the vault.

   .. _cbr_02_0004__fig4582143195315:

   **Figure 3** Configuring auto backup

   |image6|

#. (Optional) Configure automatic resource association.

   -  If you select **Configure**, in the next backup period, CBR will automatically scan all unprotected resources, associate them with the vault, and then perform backups.
   -  If you select **Skip**, CBR will not scan and associate unprotected resources with the vault you are creating.

   You can filter unprotected resources by tag. If a tag is selected, only unprotected resources with the specified tag will be associated with the vault. Or, all unprotected resources will be associated.

   If no tag is available, you can create tags on the corresponding resource page. You can search for vaults by specifying a maximum of 5 tags at a time. If you select more than one tag, the vaults with any of the specified tags will be returned.

#. (Optional) Add tags to the vault.

   Tags are key-value pairs, which are used to identify, classify, and search for vaults. Vault tags are used to filter and manage vaults only. A vault can have a maximum of 20 tags.

   :ref:`Table 1 <cbr_02_0004__cbr_02_0003_table191162312815>` describes the parameters of a tag.

   .. _cbr_02_0004__cbr_02_0003_table191162312815:

   .. table:: **Table 1** Tag parameter description

      +-----------------------+------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                            | Example Value         |
      +=======================+========================================================================+=======================+
      | Key                   | Each tag has a unique key. You can customize a key.                    | Key_0001              |
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

   The name must contain 1 to 64 characters including digits, letters, underscores (_), or hyphens (-), for example, **vault-612c**. See :ref:`Figure 4 <cbr_02_0004__fig13429133818817>`.

   .. _cbr_02_0004__fig13429133818817:

   .. figure:: /_static/images/en-us_image_0251456277.png
      :alt: **Figure 4** Setting the vault name

      **Figure 4** Setting the vault name

   .. note::

      You can also use the default name **vault\_**\ *xxxx*.

#. Complete the creation as prompted.

#. Go back to the **Cloud Disk Backups** page. You can see the created vault in the vault list.

   You can associate disks to the new vault or perform backup for the disks. For details, see :ref:`Vault Management <cbr_03_0002>`.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image3| image:: /_static/images/en-us_image_0000002124587690.png
.. |image4| image:: /_static/images/en-us_image_0000002021491294.png
.. |image5| image:: /_static/images/en-us_image_0000001186235530.png
.. |image6| image:: /_static/images/en-us_image_0000001231755471.png
