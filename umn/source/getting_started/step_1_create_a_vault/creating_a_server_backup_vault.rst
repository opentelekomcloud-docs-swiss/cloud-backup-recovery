:original_name: cbr_02_0003.html

.. _cbr_02_0003:

Creating a Server Backup Vault
==============================

This section describes how to create a server backup vault.

Procedure
---------

#. Log in to CBR Console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select your region and project.
   c. Choose **Storage** > **Cloud Backup and Recovery**. Select a backup tab from the left navigation pane.

#. In the upper right corner of the page, click **Create Server Backup Vault**.

#. Select a protection type.

   -  **Backup**: The created vault is a server backup vault, which stores cloud server backups.

#. (Optional) In the server list, select the servers or disks you want to back up. After the servers or disks are selected, they are added to the list of selected servers. See :ref:`Figure 1 <cbr_02_0003__fig204531717131710>`. You may also select only some of the disks of a server and associate them with the vault.

   .. _cbr_02_0003__fig204531717131710:

   **Figure 1** Selecting servers

   |image2|

   .. note::

      -  The selected servers must have not been associated with another vault and must be in the **Running** or **Stopped** state.
      -  You can associate servers with the vault you are creating if you skip this step.

#. Specify the vault capacity, which ranges from 10 GB to 10485760 GB. You need to properly plan the vault capacity, which must be at least the same as the size of the servers you want to back up. Also, if automatic association is enabled and a backup policy is applied to the vault, more capacity is required.

   As the vault's used space grows, you can expand the vault capacity when it is not enough. See :ref:`Figure 2 <cbr_02_0003__fig179361847142520>`.

   .. _cbr_02_0003__fig179361847142520:

   **Figure 2** Setting the vault capacity

   |image3|

#. Configure automatic backup. See :ref:`Figure 3 <cbr_02_0003__fig4582143195315>`.

   -  If you select **Configure**, you must then select an existing backup policy or create a new one. After the vault is created, the system associates the vault with this backup policy, and all servers associated with this vault will be automatically backed up based on this policy.
   -  If you select **Skip**, servers associated with this vault will not be automatically backed up until you apply a backup policy to the vault.

   .. _cbr_02_0003__fig4582143195315:

   **Figure 3** Configuring automatic backup

   |image4|

#. (Optional) Configure automatic resource association.

   -  If you select **Configure**, resources that are not backed up will be automatically associated with the vault you are creating. After association, the resources will be backed up according to the backup policy applied to the vault.
   -  If you select **Skip**, resources will not be automatically associated with the vault you are creating.

#. (Optional) Add tags to the vault.

   A tag is represented in the form of a key-value pair. Tags are used to identify, classify, and search for vaults. Vault tags are used to filter and manage vaults only. A vault can have a maximum of 10 tags.

   :ref:`Table 1 <cbr_02_0003__table191162312815>` describes the parameters of a tag.

   .. _cbr_02_0003__table191162312815:

   .. table:: **Table 1** Tag parameter description

      +-----------------------+-----------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                               | Example Value         |
      +=======================+===========================================================================================================+=======================+
      | Key                   | Each tag has a unique key. You can customize the key or select the key of an existing tag created in TMS. | Key_0001              |
      |                       |                                                                                                           |                       |
      |                       | The naming rules for a tag key are as follows:                                                            |                       |
      |                       |                                                                                                           |                       |
      |                       | -  It contains 1 to 36 Unicode characters.                                                                |                       |
      |                       | -  It can contain only letters, digits, hyphens (-), and underscores (_).                                 |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------+-----------------------+
      | Value                 | A tag value can be repetitive or left blank.                                                              | Value_0001            |
      |                       |                                                                                                           |                       |
      |                       | The naming rules for a tag value are as follows:                                                          |                       |
      |                       |                                                                                                           |                       |
      |                       | -  It contains 0 to 43 Unicode characters.                                                                |                       |
      |                       | -  It can contain only letters, digits, hyphens (-), and underscores (_).                                 |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------+-----------------------+

#. Specify a name for the vault.

   A name must contain 1 to 64 characters including digits, letters, underscores (_), or hyphens (-), for example, **vault-f61e**.

   .. note::

      You can use the default name, which is in the format of **vault\_**\ *xxxx*.

#. Complete the creation as prompted.

#. Go back to the **Cloud Server Backup** page. You can see the created vault in the vault list.

   You can associate servers with the vault and perform backup for the servers. For details, see :ref:`Querying a Vault <cbr_03_0002>`.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001231753127.png
.. |image3| image:: /_static/images/en-us_image_0000001231754033.png
.. |image4| image:: /_static/images/en-us_image_0000001186394912.png
