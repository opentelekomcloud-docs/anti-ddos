:original_name: en-us_topic_0258573747.html

.. _en-us_topic_0258573747:

Setting a Default Protection Policy for Newly Purchased Public IP Addresses
===========================================================================

After you set a default protection policy, the newly purchased public IP addresses will be protected based on the default protection policy.

Prerequisites
-------------

You have obtained an account and its password to log in to the management console.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region or project.

#. Choose **Security** > **Anti-DDoS**. The Anti-DDoS service management page is displayed.

#. The **Public IP Addresses** tab page is displayed by default. Click **Set Default Protection Policy**.


   .. figure:: /_static/images/en-us_image_0258795362.png
      :alt: **Figure 1** Setting a default protection policy for newly purchased public ip addresses

      **Figure 1** Setting a default protection policy for newly purchased public ip addresses

#. Configure the default protection policy.


   .. figure:: /_static/images/en-us_image_0258829059.png
      :alt: **Figure 2** Configuring the default protection policy

      **Figure 2** Configuring the default protection policy

   .. table:: **Table 1** Parameter description

      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                                                                                                  |
      +===================================+==============================================================================================================================================================================================================================================================================================================+
      | Traffic Cleaning Threshold        | Anti-DDoS scrubs traffic when detecting that the incoming traffic of an IP address exceeds the threshold.                                                                                                                                                                                                    |
      |                                   |                                                                                                                                                                                                                                                                                                              |
      |                                   | Configure this parameter based on your actual needs. You are advised to set the threshold to a value closest to the purchased bandwidth but not greater than the purchased bandwidth.                                                                                                                        |
      |                                   |                                                                                                                                                                                                                                                                                                              |
      |                                   | If **Traffic Cleaning Threshold** is set to **Unlimited**, your public IP addresses get almost no protection from DDoS attacks.                                                                                                                                                                              |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | CC Defense                        | -  **Disable**: disables the defense.                                                                                                                                                                                                                                                                        |
      |                                   |                                                                                                                                                                                                                                                                                                              |
      |                                   | -  **Enable**: enables the defense.                                                                                                                                                                                                                                                                          |
      |                                   |                                                                                                                                                                                                                                                                                                              |
      |                                   |    .. note::                                                                                                                                                                                                                                                                                                 |
      |                                   |                                                                                                                                                                                                                                                                                                              |
      |                                   |       CC defense is available only for clients supporting the full HTTP protocol stack because CC defense works in redirection or redirection+verification code mode. If your client does not support the full HTTP protocol stack, you are advised to disable CC defense.                                   |
      |                                   |                                                                                                                                                                                                                                                                                                              |
      |                                   | -  **HTTP Request Threshold**                                                                                                                                                                                                                                                                                |
      |                                   |                                                                                                                                                                                                                                                                                                              |
      |                                   |    This option is available only when CC defense is enabled.                                                                                                                                                                                                                                                 |
      |                                   |                                                                                                                                                                                                                                                                                                              |
      |                                   |    You are advised to set this parameter to the maximum number of HTTP requests that can be processed by the deployed service. Anti-DDoS automatically scrubs traffic if the total number of detected requests exceeds this threshold. If the value is too large, CC defense will not be triggered promptly. |
      |                                   |                                                                                                                                                                                                                                                                                                              |
      |                                   |    -  If the actual HTTP request rate is smaller than the configured value, the deployed service is able to process all HTTP requests, and Anti-DDoS does not need to be involved.                                                                                                                           |
      |                                   |    -  If the actual HTTP request rate is greater than or equal to the configured value, Anti-DDoS triggers CC defense to analyze and check each request, which affects responses to normal requests.                                                                                                         |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

   After the default protection policy is set, the newly purchased public IP addresses are protected based on the default protection policy. For details about how to adjust a configured protection policy, see :ref:`Adjusting Security Settings <en-us_topic_0204851517>`.

.. |image1| image:: /_static/images/en-us_image_0258575568.png
