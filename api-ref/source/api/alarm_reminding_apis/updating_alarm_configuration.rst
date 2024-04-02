:original_name: antiddos_02_0041.html

.. _antiddos_02_0041:

Updating Alarm Configuration
============================

Functions
---------

This API allows you to update alarm configuration, such as whether a certain type of alarms will be received, and whether alarms are received through SMS messages or emails.

URI
---

-  URI format

   POST /v2/{project_id}/warnalert/alertconfig/update

-  Parameter description

   ========== ========= ====== ===========
   Parameter  Mandatory Type   Description
   ========== ========= ====== ===========
   project_id Yes       String User ID
   ========== ========= ====== ===========

Request
-------

-  Parameter description

   +--------------+-----------+---------------------+---------------------------------------------------------------------------+
   | Parameter    | Mandatory | Type                | Description                                                               |
   +==============+===========+=====================+===========================================================================+
   | warn_config  | Yes       | List data structure | Alarm configuration                                                       |
   +--------------+-----------+---------------------+---------------------------------------------------------------------------+
   | topic_urn    | Yes       | String              | ID of an alarm group                                                      |
   +--------------+-----------+---------------------+---------------------------------------------------------------------------+
   | display_name | Yes       | String              | Specifies the name of the SMN topic used for sending alarm notifications. |
   +--------------+-----------+---------------------+---------------------------------------------------------------------------+

-  Data structure description of **warn_config**

   +-----------------+-----------------+-----------------+----------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                    |
   +=================+=================+=================+================================================================+
   | antiDDoS        | No              | Boolean         | DDoS attacks                                                   |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------+
   | bruce_force     | No              | Boolean         | Brute force cracking (system logins, FTP, and DB)              |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------+
   | remote_login    | No              | Boolean         | Alarms about remote logins                                     |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------+
   | weak_password   | No              | Boolean         | Weak passwords (system and database)                           |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------+
   | high_privilege  | No              | Boolean         | Overly high rights of a database process                       |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------+
   | back_doors      | No              | Boolean         | Webshells                                                      |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------+
   | waf             | No              | Boolean         | Reserved                                                       |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------+
   | send_frequency  | No              | Integer         | Possible values:                                               |
   |                 |                 |                 |                                                                |
   |                 |                 |                 | -  **0**: indicates that alarms are sent once a day.           |
   |                 |                 |                 | -  **1**: indicates that alarms are sent once every half hour. |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------+

   .. note::

      SFTP is more secure than FTP. To secure data transmission, use SFTP to transfer files.

Response Message
----------------

========== ====== ==========================
Parameter  Type   Description
========== ====== ==========================
error_code String Internal error code
error_msg  String Internal error description
task_id    String Task ID
========== ====== ==========================

Example
-------

-  Example request

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

-  Example response

   .. code-block::

      {
        "error_code" : "10000000",
        "error_msg" : "Ok",
        "task_id" : ""
      }

Status Code
-----------

For details, see :ref:`Status Code <antiddos_02_0031>`.
