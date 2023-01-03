:original_name: en-us_topic_0204851468.html

.. _en-us_topic_0204851468:

Viewing a Monitoring Report
===========================

Scenarios
---------

This topic describes how to view the monitoring report of an EIP, covering the current protection status, protection settings, and the traffic and anomalies within the last 24 hours.

Prerequisites
-------------

You have obtained an account and its password to log in to the management console.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the region or project.

#. Under **Security**, choose **Anti-DDoS**. The **Security Console** is displayed.

#. Select the **Public IP Addresses** tab, locate the target IP address and click **View Monitoring Report** in the **Operation** column, as shown in :ref:`Figure 1 <en-us_topic_0204851468__fig28737219154047>`

   .. _en-us_topic_0204851468__fig28737219154047:

   .. figure:: /_static/images/en-us_image_0217719594.png
      :alt: **Figure 1** Viewing a monitoring report

      **Figure 1** Viewing a monitoring report

#. On the **Monitoring Report** page, view monitoring details about a public IP address.

   -  You can view information such as the current protection status, protection settings, and the traffic and anomalies within the last 24 hours.
   -  A 24-hour defense traffic chart is generated from data points taken in five-minute intervals. It includes the following information:

      -  **Traffic (Kbps)** displays the traffic status of the selected ECS, including the incoming attack traffic and normal traffic.
      -  **Packet Rate (pps)** displays the packet rate of the selected ECS, including the attack packet rate and normal incoming packet rate.

   -  The attack event list within one day records DDoS attacks on the ECS within one day, including cleaning events and black hole events.


   .. figure:: /_static/images/en-us_image_0217782662.png
      :alt: **Figure 2** Monitoring report

      **Figure 2** Monitoring report

   .. note::

      On the **Monitoring Report** page, click |image2| to download the monitoring report about the public IP address.

.. |image1| image:: /_static/images/en-us_image_0237050217.png
.. |image2| image:: /_static/images/en-us_image_0237052378.png
