:original_name: en-us_topic_0204851508.html

.. _en-us_topic_0204851508:

Related Services
================

CTS
---

Cloud Trace Service (CTS) provides you with a history of Anti-DDoS operations. After enabling CTS, you can view all generated traces to review and audit performed Anti-DDoS operations. For details, see the *Cloud Trace Service User Guide*.

-  Anti-DDoS operations that can be recorded by CTS

   .. table:: **Table 1** Anti-DDoS operations that can be recorded by CTS

      ===================================== ==============
      Operation                             Trace Name
      ===================================== ==============
      Enabling Anti-DDoS                    openAntiddos
      Disabling Anti-DDoS                   deleteAntiddos
      Adjusting Anti-DDoS security settings updateAntiddos
      ===================================== ==============

-  Using CTS to view Anti-DDoS audit logs

   #. Log in to the management console.
   #. Click |image1| in the upper left corner to select a region or project.
   #. Select **Cloud Trace Service** under **Management & Deployment**.
   #. In the left navigation pane, choose **Trace List**.
   #. You can use filters to query traces. The following four filters are available:

      -  **Trace Source**, **Resource Type**, and **Search By**

         -  Select query conditions from the drop-down list, for example, choose **Anti-DDoS** > **anti-ddos** > **Trace name** > **openAntiddos** to query all Anti-DDoS enabling operations.
         -  **Trace name**: This option allows you to select a trace name, such as **openAntiddos**.
         -  **Resource ID**: This option allows you to select or manually enter the ID of the instance for which you want to view audit logs.
         -  **Resource name**: This option allows you to select or manually enter the name of the instance for which you want to view audit logs.

      -  **Operator**: Select a specific operator (at user level rather than tenant level).
      -  **Trace Status**: Available options include **All trace statuses**, **normal**, **warning**, and **incident**. You can only select one of them.
      -  Start time and end time: You can specify the time period to query traces.

   #. Click |image2| on the left of the record to be queried to extend its details.
   #. In the row containing the desired record, click **View Trace**.

IAM
---

Identity and Access Management (IAM) provides the permission management function for Anti-DDoS. Only users who have Anti-DDoS Administrator permissions can use Anti-DDoS. To apply for Anti-DDoS Administrator permissions, contact a user with Security Administrator permissions. For details, see the *Identity and Access Management User Guide*.

SMN
---

The Simple Message Notification (SMN) service provides the notification function. When alarm notification is enabled in Anti-DDoS, you will receive alarm messages by SMS or email if your IP address is under a DDoS attack.

For details about SMN, see the *Simple Message Notification User Guide*.

.. |image1| image:: /_static/images/en-us_image_0237050217.png
.. |image2| image:: /_static/images/en-us_image_0204851462.png
