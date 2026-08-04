:original_name: cbr_06_0008.html

.. _cbr_06_0008:

Can I Back Up a Server Deployed with Databases?
===============================================

Yes. To back up applications requiring strict consistency, such as databases and email systems, you are advised to suspend all write operations and then perform backup. If write operations cannot be suspended, you can stop the application systems or the server for offline backup. If these steps are not performed, the server's post-restoration state will resemble a restart after an unexpected power failure, and database log rollback will be triggered to maintain data consistency.
