:original_name: antiddos_02_0021.html

.. _antiddos_02_0021:

Updating Anti-DDoS Defense Policies
===================================

Functions
---------

This API enables you to update the Anti-DDoS defense policy of a specified EIP. Successfully invoking this API only means that the service node has received the update request. You need to use the task querying API to check the task execution status. For details about the task querying API, see :ref:`Querying Anti-DDoS Tasks <antiddos_02_0022>`.

URI
---

-  URI format

   PUT /v1/{project_id}/antiddos/{floating_ip_id}

-  Parameter description

   ============== ========= ====== =====================================
   Parameter      Mandatory Type   Description
   ============== ========= ====== =====================================
   project_id     Yes       String User ID
   floating_ip_id Yes       String ID corresponding to the EIP of a user
   ============== ========= ====== =====================================

Request
-------

.. table:: **Table 1** Parameter description

   +------------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------+
   | Parameter              | Mandatory       | Type            | Description                                                                                    |
   +========================+=================+=================+================================================================================================+
   | enable_L7              | No              | Boolean         | Whether to enable L7 defense                                                                   |
   +------------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------+
   | traffic_pos_id         | Yes             | Integer         | Position ID of traffic. The value ranges from 1 to 9, or 99, or 33 to 36.                      |
   +------------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------+
   | http_request_pos_id    | Yes             | Integer         | Position ID of number of HTTP requests. The value ranges from 1 to 15 and 33 to 36.            |
   +------------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------+
   | cleaning_access_pos_id | Yes             | Integer         | Position ID of access limit during cleaning. The value ranges from 1 to 8, or 99, or 33 to 36. |
   +------------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------+
   | app_type_id            | No              | Integer         | Application type ID. Possible values:                                                          |
   |                        |                 |                 |                                                                                                |
   |                        |                 |                 | -  0                                                                                           |
   |                        |                 |                 | -  1                                                                                           |
   +------------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------+

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

      PUT /v1/67641fe6886f43fcb78edbbf0ad0b99f/antiddos/ee0c854e-082f-499e-b7d8-1b42c22781af

   .. code-block::

      {
          "enable_L7":false,
          "traffic_pos_id":2,
          "http_request_pos_id":1,
          "cleaning_access_pos_id":1,
          "app_type_id":1
      }

-  Example response

   .. code-block::

      {
         "error_code": "10000000",
         "error_description": "Task has been received and is being processed.",
         "task_id": "4a4fefe7-34a1-40e2-a87c-16932af3ac4a"
      }

Status Code
-----------

See :ref:`Status Code <antiddos_02_0031>`.
