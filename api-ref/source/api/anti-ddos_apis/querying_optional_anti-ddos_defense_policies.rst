:original_name: antiddos_02_0017.html

.. _antiddos_02_0017:

Querying Optional Anti-DDoS Defense Policies
============================================

Functions
---------

This API allows you to query optional Anti-DDoS defense policies. Based on your service, you can select a policy for Anti-DDoS traffic scrubbing.

URI
---

-  URI format

   GET /v1/{project_id}/antiddos/query_config_list

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

   +-------------------------+---------------------+------------------------------------------+
   | Parameter               | Type                | Description                              |
   +=========================+=====================+==========================================+
   | traffic_limited_list    | List data structure | List of traffic limits                   |
   +-------------------------+---------------------+------------------------------------------+
   | http_limited_list       | List data structure | List of HTTP limits                      |
   +-------------------------+---------------------+------------------------------------------+
   | connection_limited_list | List data structure | List of limits of numbers of connections |
   +-------------------------+---------------------+------------------------------------------+

-  Data structure description of **traffic_limited_list**

   ================== ======= =========================================
   Parameter          Type    Description
   ================== ======= =========================================
   traffic_pos_id     Integer Position ID of traffic
   traffic_per_second Integer Threshold of traffic per second (Mbit/s)
   packet_per_second  Integer Threshold of number of packets per second
   ================== ======= =========================================

-  Data structure description of **http_limited_list**

   +------------------------+---------+-------------------------------------------------+
   | Parameter              | Type    | Description                                     |
   +========================+=========+=================================================+
   | http_request_pos_id    | Integer | Position ID of number of HTTP requests          |
   +------------------------+---------+-------------------------------------------------+
   | http_packet_per_second | Integer | Threshold of number of HTTP requests per second |
   +------------------------+---------+-------------------------------------------------+

-  Data structure description of **connection_limited_list**

   +--------------------------+---------+----------------------------------------------------+
   | Parameter                | Type    | Description                                        |
   +==========================+=========+====================================================+
   | cleaning_access_pos_id   | Integer | Position ID of access limit during cleaning        |
   +--------------------------+---------+----------------------------------------------------+
   | new_connection_limited   | Integer | Number of new connections of a source IP address   |
   +--------------------------+---------+----------------------------------------------------+
   | total_connection_limited | Integer | Total number of connections of a source IP address |
   +--------------------------+---------+----------------------------------------------------+

Example
-------

-  Example request

   .. code-block:: text

      GET /v1/67641fe6886f43fcb78edbbf0ad0b99f/antiddos/query_config_list

-  Example response

   .. code-block::

      {
        "traffic_limited_list": [
          {
            "traffic_pos_id": 1,
            "traffic_per_second": 10,
            "packet_per_second": 2000
          },
          {
            "traffic_pos_id": 2,
            "traffic_per_second": 30,
            "packet_per_second": 6000
          },
          {
            "traffic_pos_id": 3,
            "traffic_per_second": 50,
            "packet_per_second": 10000
          },
          {
            "traffic_pos_id": 4,
            "traffic_per_second": 70,
            "packet_per_second": 15000
          },
          {
            "traffic_pos_id": 5,
            "traffic_per_second": 100,
            "packet_per_second": 20000
          },
          {
            "traffic_pos_id": 6,
            "traffic_per_second": 150,
            "packet_per_second": 25000
          },
          {
            "traffic_pos_id": 7,
            "traffic_per_second": 200,
            "packet_per_second": 35000
          },
          {
            "traffic_pos_id": 8,
            "traffic_per_second": 250,
            "packet_per_second": 50000
          },
          {
            "traffic_pos_id": 9,
            "traffic_per_second": 300,
            "packet_per_second": 70000
          }
        ],
        "http_limited_list": [
          {
            "http_request_pos_id": 1,
            "http_packet_per_second": 100
          },
          {
            "http_request_pos_id": 2,
            "http_packet_per_second": 150
          },
          {
            "http_request_pos_id": 3,
            "http_packet_per_second": 240
          },
          {
            "http_request_pos_id": 4,
            "http_packet_per_second": 350
          },
          {
            "http_request_pos_id": 5,
            "http_packet_per_second": 480
          },
          {
            "http_request_pos_id": 6,
            "http_packet_per_second": 550
          },
          {
            "http_request_pos_id": 7,
            "http_packet_per_second": 700
          },
          {
            "http_request_pos_id": 8,
            "http_packet_per_second": 850
          },
          {
            "http_request_pos_id": 9,
            "http_packet_per_second": 1000
          },
          {
            "http_request_pos_id": 10,
            "http_packet_per_second": 1500
          },
          {
            "http_request_pos_id": 11,
            "http_packet_per_second": 2000
          },
          {
            "http_request_pos_id": 12,
            "http_packet_per_second": 3000
          },
          {
            "http_request_pos_id": 13,
            "http_packet_per_second": 5000
          },
          {
            "http_request_pos_id": 14,
            "http_packet_per_second": 10000
          },
          {
            "http_request_pos_id": 15,
            "http_packet_per_second": 20000
          }
        ],
        "connection_limited_list": [
          {
            "cleaning_access_pos_id": 1,
            "new_connection_limited": 10,
            "total_connection_limited": 30
          },
          {
            "cleaning_access_pos_id": 2,
            "new_connection_limited": 20,
            "total_connection_limited": 100
          },
          {
            "cleaning_access_pos_id": 3,
            "new_connection_limited": 30,
            "total_connection_limited": 200
          },
          {
            "cleaning_access_pos_id": 4,
            "new_connection_limited": 40,
            "total_connection_limited": 250
          },
          {
            "cleaning_access_pos_id": 5,
            "new_connection_limited": 50,
            "total_connection_limited": 300
          },
          {
            "cleaning_access_pos_id": 6,
            "new_connection_limited": 60,
            "total_connection_limited": 500
          },
          {
            "cleaning_access_pos_id": 7,
            "new_connection_limited": 70,
            "total_connection_limited": 600
          },
          {
            "cleaning_access_pos_id": 8,
            "new_connection_limited": 80,
            "total_connection_limited": 700
          }
        ],
        "extend_ddos_config": [
          {
            "new_connection_limited": 80,
            "total_connection_limited": 700,
            "http_packet_per_second": 500000,
            "traffic_per_second": 1000,
            "packet_per_second": 200000,
            "setID": 33
          },
          {
            "new_connection_limited": 80,
            "total_connection_limited": 700,
            "http_packet_per_second": 500000,
            "traffic_per_second": 2000,
            "packet_per_second": 200000,
            "setID": 34
          },
          {
            "new_connection_limited": 80,
            "total_connection_limited": 700,
            "http_packet_per_second": 500000,
            "traffic_per_second": 5000,
            "packet_per_second": 400000,
            "setID": 35
          },
          {
            "new_connection_limited": 80,
            "total_connection_limited": 700,
            "http_packet_per_second": 0,
            "traffic_per_second": 0,
            "packet_per_second": 0,
            "setID": 36
          }
        ]
      }

.. note::

   The **extend_ddos_config** field displays information about Anti-DDoS defense policies set by users based on their needs.

Status Code
-----------

See :ref:`Status Code <antiddos_02_0031>`.
