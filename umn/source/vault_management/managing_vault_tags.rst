:original_name: cbr_03_0010.html

.. _cbr_03_0010:

Managing Vault Tags
===================

You can add, edit, or delete tags of a vault. Vault tags are used to filter and manage vaults only.

Procedure
---------

#. Log in to the CBR console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select a region.
   c. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**. Select a backup type from the left navigation pane.

#. On the **Vaults** tab, click the name of the target vault and then select the **Tags** tab.

   -  Adding a tag

      a. Click **Add Tag** in the upper left corner.

      b. In the displayed dialog box, enter the key and value of the new tag.

         Tags are key-value pairs, which are used to identify, classify, and search for vaults. You can add a maximum of 20 tags for a vault, and vault tags are only used for vault search and management. See :ref:`Figure 1 <cbr_03_0010__fig1898914563297>`.

         .. _cbr_03_0010__fig1898914563297:

         .. figure:: /_static/images/en-us_image_0251474017.png
            :alt: **Figure 1** Adding a tag

            **Figure 1** Adding a tag

         :ref:`Table 1 <cbr_03_0010__table103661428132915>` describes the parameters of a tag.

         .. _cbr_03_0010__table103661428132915:

         .. table:: **Table 1** Tag parameter description

            +-----------------------+-------------------------------------------------------------------------+-----------------------+
            | Parameter             | Description                                                             | Example Value         |
            +=======================+=========================================================================+=======================+
            | Key                   | Tag key. Each tag of a vault has a unique key. You can customize a key. | Key_0001              |
            |                       |                                                                         |                       |
            |                       | A tag key:                                                              |                       |
            |                       |                                                                         |                       |
            |                       | -  Can contain 1 to 36 Unicode characters.                              |                       |
            |                       | -  Can contain only letters, digits, hyphens (-), and underscores (_).  |                       |
            +-----------------------+-------------------------------------------------------------------------+-----------------------+
            | Value                 | A tag value can be repetitive or left blank.                            | Value_0001            |
            |                       |                                                                         |                       |
            |                       | A tag value:                                                            |                       |
            |                       |                                                                         |                       |
            |                       | -  Can contain 0 to 43 Unicode characters.                              |                       |
            |                       | -  Can contain only letters, digits, hyphens (-), and underscores (_).  |                       |
            +-----------------------+-------------------------------------------------------------------------+-----------------------+

      c. Click **OK**.

   -  Editing a tag

      a. In the **Operation** column of the tag that you want to edit, click **Edit**.
      b. In the displayed **Edit Tag** dialog box, enter a new tag value. :ref:`Table 1 <cbr_03_0010__table103661428132915>` describes the parameters.
      c. Click **OK**.

   -  Deleting a tag

      a. In the **Operation** column of the tag that you want to delete, click **Delete**.
      b. In the displayed dialog box, confirm the deletion information.
      c. Click **Yes**.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
