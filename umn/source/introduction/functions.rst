:original_name: en-us_topic_0125048639.html

.. _en-us_topic_0125048639:

Functions
=========

The Anti-DDoS traffic cleaning service (Anti-DDoS for short) defends elastic IP addresses (EIPs) against network- and application-layer distributed denial of service (DDoS) attacks and sends alarms immediately when detecting an attack. In addition, Anti-DDoS improves the utilization of bandwidth and ensures the stable running of users' services.

Anti-DDoS monitors the service traffic from the Internet to EIPs to detect attack traffic in real time. It then cleans attack traffic according to user-configured defense policies so that services run as normal. In addition, monitoring reports are generated, presenting users with clear network security evaluations.

Anti-DDoS helps users cope with traffic attacks with ease. It can precisely identify connection exhaustion and slow-connection attacks and can help users defend against the following attacks:

-  Web server attacks

   Such as SYN flood, HTTP flood, Challenge Collapsar (CC), and slow-connection attacks

-  Game attacks

   Such as User Datagram Protocol (UDP) flood, SYN flood, Transmission Control Protocol (TCP), and fragment attacks

-  HTTPS server attacks

   Such as SSL DoS and DDoS attacks

-  DNS server attacks

   Such as attacks targeted at vulnerabilities in the Domain Name Server (DNS) protocol stack, DNS reflection attacks, DNS flood attacks, and DNS cache-miss attacks

Anti-DDoS also provides the following functions:

-  Providing monitoring records for each EIP, including the current defense status, current defense configurations, and the last 24 hours' traffic and abnormalities.
-  Providing attack statistics reports on all protected EIPs, covering the traffic cleaning frequency, cleaned traffic amount, top 10 attacked EIPs, and number of blocked attacks.
