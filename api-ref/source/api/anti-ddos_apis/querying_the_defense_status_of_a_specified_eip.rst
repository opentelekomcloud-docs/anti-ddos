:original_name: antiddos_02_0024.html

.. _antiddos_02_0024:

Querying the Defense Status of a Specified EIP
==============================================

Functions
---------

This API allows you to query the defense status of a specified EIP.

URI
---

-  URI format

   GET /v1/{project_id}/antiddos/{floating_ip_id}/status

-  Parameter description

   ============== ========= ====== =====================================
   Parameter      Mandatory Type   Description
   ============== ========= ====== =====================================
   project_id     Yes       String User ID
   floating_ip_id Yes       String ID corresponding to the EIP of a user
   ============== ========= ====== =====================================

Request
-------

**Request parameters**

None

Response
--------

-  Parameter description

   +-----------------+-----------------+-----------------+----------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                          |
   +=================+=================+=================+======================================================================+
   | status          | Yes             | String          | Defense status, the possible value of which is one of the following: |
   |                 |                 |                 |                                                                      |
   |                 |                 |                 | -  **normal**: indicates that the defense status is normal.          |
   |                 |                 |                 | -  **configging**: indicates that defense is being configured.       |
   |                 |                 |                 | -  **notConfig**: indicates that defense is not configured.          |
   |                 |                 |                 | -  **packetcleaning**: indicates that traffic cleaning is underway.  |
   |                 |                 |                 | -  **packetdropping**: indicates that traffic is discarded.          |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------+

Example
-------

-  Example request

   .. code-block:: text

      GET /v1/67641fe6886f43fcb78edbbf0ad0b99f/antiddos/1df977c2-fdc6-4483-bc1c-ba46829f57b8/status

-  Example response

   .. code-block::

      {"status": "normal"}

Status Code
-----------

See :ref:`Status Code <antiddos_02_0031>`.
