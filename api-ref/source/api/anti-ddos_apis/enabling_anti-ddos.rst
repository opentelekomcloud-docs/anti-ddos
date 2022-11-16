:original_name: antiddos_02_0018.html

.. _antiddos_02_0018:

Enabling Anti-DDoS
==================

Functions
---------

This asynchronous API allows you to enable the Anti-DDoS traffic scrubbing. Successfully invoking this API only means that the service node has received the enabling request. You need to use the task querying API to check the task execution status. For details about the task querying API, see :ref:`Querying Anti-DDoS Tasks <antiddos_02_0022>`.

URI
---

-  URI format

   POST /v1/{project_id}/antiddos/{floating_ip_id}

-  Parameter description

   +----------------+-----------+--------+------------------------------------------------------------+
   | Parameter      | Mandatory | Type   | Description                                                |
   +================+===========+========+============================================================+
   | project_id     | Yes       | String | User ID                                                    |
   +----------------+-----------+--------+------------------------------------------------------------+
   | floating_ip_id | Yes       | String | ID corresponding to the Elastic IP Address (EIP) of a user |
   +----------------+-----------+--------+------------------------------------------------------------+

Request
-------

.. table:: **Table 1** Parameter description

   +------------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------+
   | Parameter              | Mandatory       | Type            | Description                                                                             |
   +========================+=================+=================+=========================================================================================+
   | enable_L7              | No              | Boolean         | Whether to enable L7 defense                                                            |
   +------------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------+
   | traffic_pos_id         | Yes             | Integer         | Position ID of traffic. The value ranges from 1 to 9 and 33 to 36.                      |
   +------------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------+
   | http_request_pos_id    | Yes             | Integer         | Position ID of number of HTTP requests. The value ranges from 1 to 15 and 33 to 36.     |
   +------------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------+
   | cleaning_access_pos_id | Yes             | Integer         | Position ID of access limit during cleaning. The value ranges from 1 to 8 and 33 to 36. |
   +------------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------+
   | app_type_id            | No              | Integer         | Application type ID. Possible values:                                                   |
   |                        |                 |                 |                                                                                         |
   |                        |                 |                 | -  0                                                                                    |
   |                        |                 |                 | -  1                                                                                    |
   +------------------------+-----------------+-----------------+-----------------------------------------------------------------------------------------+

.. note::

   If values of **traffic_pos_id**, **http_request_pos_id**, **cleaning_access_pos_id** are set between **33 to 36**, their values must be the same.

Response
--------

.. table:: **Table 2** Parameter description

   +-----------------------+-----------------------+----------------------------------------------------------------------------------+
   | Name                  | Type                  | Description                                                                      |
   +=======================+=======================+==================================================================================+
   | error_code            | String                | Internal error code                                                              |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------+
   | error_description     | String                | Internal error description                                                       |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------+
   | task_id               | String                | ID of a task. This ID can be used to query the status of the task.               |
   |                       |                       |                                                                                  |
   |                       |                       | This field is reserved for use in task auditing later. It is temporarily unused. |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------+

Example
-------

-  Example request

   .. code-block:: text

      POST /v1/67641fe6886f43fcb78edbbf0ad0b99f/antiddos/1df977c2-fdc6-4483-bc1c-ba46829f57b8

   .. code-block::

      {
          "enable_L7":true,
          "traffic_pos_id":1,
          "http_request_pos_id":1,
          "cleaning_access_pos_id":1,
          "app_type_id":1
      }

-  Example response

   .. code-block::

      {
         "error_code": "10000000",
         "error_description": "Task has been received and is being processed.",
         "task_id": "94e17e18-5b2c-40c6-a218-8ec5134e32a5"
      }

Status Code
-----------

See :ref:`Status Code <antiddos_02_0031>`.
