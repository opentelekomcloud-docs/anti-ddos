:original_name: antiddos_02_0029.html

.. _antiddos_02_0029:

Querying Alarm Configuration
============================

Functions
---------

This API allows you to query alarm configuration, such as whether a certain type of alarms will be received, and whether alarms are received through SMS messages or emails.

URI
---

-  URI format

   GET /v2/{project_id}/warnalert/alertconfig/query

-  Parameter description

   ========== ========= ====== ===========
   Parameter  Mandatory Type   Description
   ========== ========= ====== ===========
   project_id Yes       String User ID
   ========== ========= ====== ===========

Request
-------

**Request parameters**

None

Response
--------

-  Parameter description

   +--------------+---------------------+---------------------------------------------------------------------------+
   | Parameter    | Type                | Description                                                               |
   +==============+=====================+===========================================================================+
   | warn_config  | List data structure | Alarm configuration                                                       |
   +--------------+---------------------+---------------------------------------------------------------------------+
   | topic_urn    | String              | ID of an alarm group                                                      |
   +--------------+---------------------+---------------------------------------------------------------------------+
   | display_name | String              | Specifies the name of the SMN topic used for sending alarm notifications. |
   +--------------+---------------------+---------------------------------------------------------------------------+

-  Data structure description of **warn_config**

   +-----------------------+-----------------------+----------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                    |
   +=======================+=======================+================================================================+
   | antiDDoS              | Boolean               | DDoS attacks                                                   |
   +-----------------------+-----------------------+----------------------------------------------------------------+
   | bruce_force           | Boolean               | Brute force cracking (system logins, FTP, and DB)              |
   +-----------------------+-----------------------+----------------------------------------------------------------+
   | remote_login          | Boolean               | Alarms about remote logins                                     |
   +-----------------------+-----------------------+----------------------------------------------------------------+
   | weak_password         | Boolean               | Weak passwords (system and database)                           |
   +-----------------------+-----------------------+----------------------------------------------------------------+
   | high_privilege        | Boolean               | Overly high rights of a database process                       |
   +-----------------------+-----------------------+----------------------------------------------------------------+
   | back_doors            | Boolean               | Webshells                                                      |
   +-----------------------+-----------------------+----------------------------------------------------------------+
   | waf                   | Boolean               | Reserved field                                                 |
   +-----------------------+-----------------------+----------------------------------------------------------------+
   | send_frequency        | Integer               | Possible values:                                               |
   |                       |                       |                                                                |
   |                       |                       | -  **0**: indicates that alarms are sent once a day.           |
   |                       |                       | -  **1**: indicates that alarms are sent once every half hour. |
   +-----------------------+-----------------------+----------------------------------------------------------------+

Example
-------

-  Example request

   .. code-block:: text

      GET /v2/67641fe6886f43fcb78edbbf0ad0b99f/warnalert/alertconfig/query

-  Example response

   .. code-block::

      {
         "warn_config":    {
            "antiDDoS": true,
            "bruce_force": false,
            "remote_login": false,
            "weak_password": false,
            "high_privilege": false,
            "back_doors": false,
            "waf": false
         },
         "topic_urn": "urn:smn:eu-de:67641fe6886f43fcb78edbbf0ad0b99f:test_soft",
         "display_name": "group_1"
      }

   .. note::

      SFTP is more secure than FTP. To secure data transmission, use SFTP to transfer files.

Status Code
-----------

See :ref:`Status Code <antiddos_02_0031>`.
