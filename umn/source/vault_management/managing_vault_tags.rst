:original_name: cbr_03_0010.html

.. _cbr_03_0010:

Managing Vault Tags
===================

You can add tags to a vault as well as edit and delete these tags. Vault tags are used to filter and manage vaults only.

Procedure
---------

#. Log in to CBR Console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select your region and project.
   c. Choose **Storage** > **Cloud Backup and Recovery**. Select a backup tab from the left navigation pane.

#. Click the name of a vault and select the **Tag** tab in the displayed vault information page.

   -  Adding a tag

      a. Click **Add Tag** in the upper left corner.

      b. In the dialog box that is displayed, set the key and value of the new tag.

         A tag is represented in the form of a key-value pair. Tags are used to identify, classify, and search for cloud resources. Vault tags are used to filter and manage vaults only. A vault can have a maximum of 10 tags. See :ref:`Figure 1 <cbr_03_0010__fig1898914563297>`.

         .. _cbr_03_0010__fig1898914563297:

         .. figure:: /_static/images/en-us_image_0251474017.png
            :alt: **Figure 1** Adding a tag

            **Figure 1** Adding a tag

         :ref:`Table 1 <cbr_03_0010__table103661428132915>` describes parameters of a tag.

         .. _cbr_03_0010__table103661428132915:

         .. table:: **Table 1** Tag parameter description

            +-----------------------+-------------------------------------------------------------------------------------------------------------------------------+-----------------------+
            | Parameter             | Description                                                                                                                   | Example Value         |
            +=======================+===============================================================================================================================+=======================+
            | Key                   | Tag key. Each tag of a vault has a unique key. You can customize the key or select the key of an existing tag created in TMS. | Key_0001              |
            |                       |                                                                                                                               |                       |
            |                       | The naming rules for a tag key are as follows:                                                                                |                       |
            |                       |                                                                                                                               |                       |
            |                       | -  It contains 1 to 36 Unicode characters.                                                                                    |                       |
            |                       | -  It can contain only letters, digits, hyphens (-), and underscores (_).                                                     |                       |
            +-----------------------+-------------------------------------------------------------------------------------------------------------------------------+-----------------------+
            | Value                 | A tag value can be repetitive or left blank.                                                                                  | Value_0001            |
            |                       |                                                                                                                               |                       |
            |                       | The naming rules for a tag value are as follows:                                                                              |                       |
            |                       |                                                                                                                               |                       |
            |                       | -  It contains 0 to 43 Unicode characters.                                                                                    |                       |
            |                       | -  It can contain only letters, digits, hyphens (-), and underscores (_).                                                     |                       |
            +-----------------------+-------------------------------------------------------------------------------------------------------------------------------+-----------------------+

      c. Click **OK**.

   -  Editing a tag

      a. In the **Operation** column of the tag that you want to edit, click **Edit**.
      b. In the **Edit Tag** dialog box that is displayed, modify the tag value. :ref:`Table 1 <cbr_03_0010__table103661428132915>` describes the parameters.
      c. Click **OK**.

   -  Deleting a tag

      a. In the **Operation** column of the tag that you want to delete, click **Delete**.
      b. In the dialog box that is displayed, confirm the deletion information.
      c. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
