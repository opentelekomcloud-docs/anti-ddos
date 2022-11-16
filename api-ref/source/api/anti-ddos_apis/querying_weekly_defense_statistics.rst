:original_name: antiddos_02_0027.html

.. _antiddos_02_0027:

Querying Weekly Defense Statistics
==================================

Functions
---------

This API allows you to query weekly defense statistics about all your IP addresses, including the number of intercepted DDoS attacks, number of attacks, and ranking by the number of attacks. Currently, you can query weekly statistics up to four weeks before the current time. Data older than four weeks cannot be queried.

URI
---

-  URI format

   GET /v1/{project_id}/antiddos/weekly

   .. note::

      You can use **?** and **&** behind the URI to add query conditions, as shown in the request example.

-  Parameter description

   ========== ========= ====== ===========
   Parameter  Mandatory Type   Description
   ========== ========= ====== ===========
   project_id Yes       String User ID
   ========== ========= ====== ===========

Request
-------

.. table:: **Table 1** Parameter description

   ================= ========= ====== ================================
   Parameter         Mandatory Type   Description
   ================= ========= ====== ================================
   period_start_date No        String Start date of a seven-day period
   ================= ========= ====== ================================

Response
--------

-  Parameter description

   +----------------------+----------------+------------------------------------------+
   | Name                 | Type           | Description                              |
   +======================+================+==========================================+
   | ddos_intercept_times | Integer        | Number of DDoS attacks blocked in a week |
   +----------------------+----------------+------------------------------------------+
   | weekdata             | Data structure | Number of attacks in a week              |
   +----------------------+----------------+------------------------------------------+
   | top10                | Data structure | Top 10 attacked IP addresses             |
   +----------------------+----------------+------------------------------------------+

-  Data structure description of **weekdata**

   +----------------------+-----------+--------------+--------------------------------------+
   | Parameter            | Mandatory | Type         | Description                          |
   +======================+===========+==============+======================================+
   | ddos_intercept_times | Yes       | Integer      | Number of DDoS attacks blocked       |
   +----------------------+-----------+--------------+--------------------------------------+
   | ddos_blackhole_times | Yes       | Integer      | Number of DDoS black holes           |
   +----------------------+-----------+--------------+--------------------------------------+
   | max_attack_bps       | Yes       | Integer      | Maximum attack traffic               |
   +----------------------+-----------+--------------+--------------------------------------+
   | max_attack_conns     | Yes       | Integer      | Maximum number of attack connections |
   +----------------------+-----------+--------------+--------------------------------------+
   | period_start_date    | Yes       | Long integer | Start time                           |
   +----------------------+-----------+--------------+--------------------------------------+

-  Data structure description of **top10**

   +---------------------+-----------+---------+-----------------------------------------------------------------------------------+
   | Parameter           | Mandatory | Type    | Description                                                                       |
   +=====================+===========+=========+===================================================================================+
   | floating_ip_address | Yes       | String  | EIP                                                                               |
   +---------------------+-----------+---------+-----------------------------------------------------------------------------------+
   | times               | Yes       | Integer | Number of DDoS attacks intercepted, including cleaning operations and black holes |
   +---------------------+-----------+---------+-----------------------------------------------------------------------------------+

Example
-------

-  Example request

   .. code-block:: text

      GET /v1/67641fe6886f43fcb78edbbf0ad0b99f/antiddos/weekly?period_start_date=1006510306

-  Example response

   .. code-block::

      {
         "ddos_intercept_times": 23,
         "weekdata": [
            {
               "ddos_intercept_times": 0,
               "ddos_blackhole_times": 0,
               "max_attack_bps": 0,
               "max_attack_conns": 0,
               "period_start_date": 1474214461651
            },
            {
               "ddos_intercept_times": 0,
               "ddos_blackhole_times": 0,
               "max_attack_bps": 0,
               "max_attack_conns": 0,
               "period_start_date": 1474300861651
            },
            {
               "ddos_intercept_times": 0,
               "ddos_blackhole_times": 0,
               "max_attack_bps": 0,
               "max_attack_conns": 0,
               "period_start_date": 1474387261651
            },
            {
               "ddos_intercept_times": 0,
               "ddos_blackhole_times": 0,
               "max_attack_bps": 0,
               "max_attack_conns": 0,
               "period_start_date": 1474473661651
            },
            {
               "ddos_intercept_times": 0,
               "ddos_blackhole_times": 0,
               "max_attack_bps": 0,
               "max_attack_conns": 0,
               "period_start_date": 1474560061651
            },
            {
               "ddos_intercept_times": 2,
               "ddos_blackhole_times": 0,
               "max_attack_bps": 16375,
               "max_attack_conns": 0,
               "period_start_date": 1474646461651
            },
            {
               "ddos_intercept_times": 1,
               "ddos_blackhole_times": 0,
               "max_attack_bps": 0,
               "max_attack_conns": 0,
               "period_start_date": 1474732861651
            }
         ],
         "top10": [
            {
               "floating_ip_address": "192.168.44.69",
               "times": 23
            }
         ]
      }

Status Code
-----------

See :ref:`Status Code <antiddos_02_0031>`.
