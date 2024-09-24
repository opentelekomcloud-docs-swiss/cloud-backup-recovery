:original_name: cbr_02_0003.html

.. _cbr_02_0003:

Creating a Server Backup Vault
==============================

This section describes how to create a server backup vault.

Procedure
---------

#. Log in to the CBR console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select a region.
   c. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**. Select a backup type from the left navigation pane.

#. In the upper right corner of the page, click **Create Server Backup Vault**.

#. Select a protection type.

   -  **Backup**: A server backup vault stores server backups.

#. (Optional) In the server list, select the servers or disks you want to back up. After the servers or disks are selected, they are added to the list of selected servers. See :ref:`Figure 1 <cbr_02_0003__fig204531717131710>`. You can also select specific disks on a server and associate them with the vault.

   .. important::

      To avoid data inconsistency after restoration, you are advised to back up the entire server.

      If you want to back up only some of the disks to reduce costs, ensure that data on the backed up disks does not depend on the disks that are not backed up. Or, data inconsistency may occur.

      For example, the data of an Oracle database is scattered across different disks. If only some of the disks are backed up, restoration restores only the data of the disks that have been backed up, with data on the rest of the disks unchanged. As a result, the data may be inconsistent and the Oracle database may fail to start.

   .. _cbr_02_0003__fig204531717131710:

   **Figure 1** Selecting servers

   |image3|

   .. note::

      -  The selected servers must have not been associated with any vault and must be in the **Running** or **Stopped** state.
      -  You can also associate servers with the vault you are creating later if you skip this step.

#. Specify a vault capacity ranging from 10 GB to 10,485,760 GB. Properly plan the vault capacity, which must be at least the same as the size of the servers you want to back up. Also, if automatic association is enabled and a backup policy is applied to the vault, more capacity is required.

   As the vault's used space grows, you can expand the vault capacity if it becomes insufficient. See :ref:`Figure 2 <cbr_02_0003__fig179361847142520>`.

   .. _cbr_02_0003__fig179361847142520:

   **Figure 2** Setting the vault capacity

   |image4|

#. Configure auto backup. See :ref:`Figure 3 <cbr_02_0003__fig4582143195315>`.

   -  If you select **Configure**, you must then select an existing backup policy or create a new policy. After the vault is created, CBR will apply the policy to this vault, and all servers associated with this vault will be automatically backed up based on this policy.
   -  If you select **Skip**, servers associated with this vault will not be automatically backed up until you apply a backup policy to the vault.

   .. _cbr_02_0003__fig4582143195315:

   **Figure 3** Configuring auto backup

   |image5|

#. (Optional) Configure automatic resource association.

   -  If you select **Configure**, in the next backup period, CBR will automatically scan all unprotected resources, associate them with the vault, and then perform backups.
   -  If you select **Skip**, CBR will not scan and associate unprotected resources with the vault you are creating.

   If no tag is available, you can create tags on the corresponding resource page. You can search for vaults by specifying a maximum of 5 tags at a time. If you select more than one tag, the vaults with any of the specified tags will be returned.

#. (Optional) Add tags to the vault.

   Tags are key-value pairs, which are used to identify, classify, and search for vaults. You can add a maximum of 20 tags for a vault, and vault tags are only used for vault search and management.

   :ref:`Table 1 <cbr_02_0003__table191162312815>` describes the parameters of a tag.

   .. _cbr_02_0003__table191162312815:

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

   The name must contain 1 to 64 characters including digits, letters, underscores (_), or hyphens (-), for example, **vault-f61e**.

   .. note::

      You can also use the default name **vault\_**\ *xxxx*.

#. Complete the creation as prompted.

#. Go back to the **Cloud Server Backups** page. You can see the created vault in the vault list.

   You can associate servers with the vault and perform backup for the servers. For details, see :ref:`Querying a Vault <cbr_03_0002>`.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image3| image:: /_static/images/en-us_image_0000001231753127.png
.. |image4| image:: /_static/images/en-us_image_0000001231754033.png
.. |image5| image:: /_static/images/en-us_image_0000001186394912.png
