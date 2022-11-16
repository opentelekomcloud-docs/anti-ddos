:original_name: antiddos_02_0025.html

.. _antiddos_02_0025:

Querying the Traffic of a Specified EIP
=======================================

Functions
---------

This API allows you to query the traffic of a specified EIP in the last 24 hours. Traffic is detected in five-minute intervals.

URI
---

-  URI format

   GET /v1/{project_id}/antiddos/{floating_ip_id}/daily

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

   ==== ============== ============================
   Name Type           Description
   ==== ============== ============================
   data Data structure Traffic in the last 24 hours
   ==== ============== ============================

-  Data structure description of **data**

   +--------------+-----------+--------------+----------------------------------------------------+
   | Parameter    | Mandatory | Type         | Description                                        |
   +==============+===========+==============+====================================================+
   | period_start | Yes       | Long integer | Start time                                         |
   +--------------+-----------+--------------+----------------------------------------------------+
   | bps_in       | Yes       | Integer      | Inbound traffic (bit/s)                            |
   +--------------+-----------+--------------+----------------------------------------------------+
   | bps_attack   | Yes       | Integer      | Attack traffic (bit/s)                             |
   +--------------+-----------+--------------+----------------------------------------------------+
   | total_bps    | Yes       | Integer      | Total traffic                                      |
   +--------------+-----------+--------------+----------------------------------------------------+
   | pps_in       | Yes       | Integer      | Inbound packet rate (number of packets per second) |
   +--------------+-----------+--------------+----------------------------------------------------+
   | pps_attack   | Yes       | Integer      | Attack packet rate (number of packets per second)  |
   +--------------+-----------+--------------+----------------------------------------------------+
   | total_pps    | Yes       | Integer      | Total packet rate                                  |
   +--------------+-----------+--------------+----------------------------------------------------+

Example
-------

-  Example request

   .. code-block:: text

      GET /v1/67641fe6886f43fcb78edbbf0ad0b99f/antiddos/1df977c2-fdc6-4483-bc1c-ba46829f57b8/daily

-  Example response

   .. code-block::

      {"data": [
            {
            "period_start": 1472713370609,
            "bps_in": 0,
            "bps_attack": 0,
            "total_bps": 0,
            "pps_in": 0,
            "pps_attack": 0,
            "total_pps": 0
         },


         ...


            {
            "period_start": 1472713670609,
            "bps_in": 0,
            "bps_attack": 0,
            "total_bps": 0,
            "pps_in": 0,
            "pps_attack": 0,
            "total_pps": 0
         }]
      }

Status Code
-----------

See :ref:`Status Code <antiddos_02_0031>`.
