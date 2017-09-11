
[Source](https://www.nginx.com/resources/admin-guide/ "Permalink to NGINX and NGINX Plus Admin Guide")   [翻译](https://xy2401.github.io/excerpt/nginx/admin-guide-cn/ "中文翻译")

# NGINX and NGINX Plus Admin Guide

NGINX is an open source web server and reverse proxy that excels at large-scale web integration, application security, and web acceleration. NGINX Plus extends NGINX with additional [load balancing and application delivery features][1]. The articles in the NGINX Plus Admin Guide and Tutorial will quickly show you how to use some of the most popular features of NGINX and NGINX Plus. To purchase an NGINX Plus subscription, [contact the NGINX Plus sales team][2].

## Installing NGINX

* [**Installing NGINX Plus][34]** – Obtaining and installing NGINX Plus
* [**Installing NGINX Open Source][35]** – Obtaining, compiling, and installing open source NGINX
* [**NGINX Plus on Microsoft Azure][36]** – Setting up NGINX Plus VMs to load balance and deliver applications and content in Microsoft Azure
* [**NGINX Plus on Amazon EC2][37]** – Setting up NGINX Plus AMIs to load balance and deliver applications and content in the Amazon Web Services Elastic Compute Cloud (AWS EC2)
* [**NGINX Plus on the Google Cloud Platform][38]** – Setting up NGINX Plus VMs to load balance and deliver applications and content on the Google Cloud Platform

## Getting Started

* [**Runtime control][3]** – Starting and stopping NGINX and NGINX Plus processes, including zero-downtime reconfiguration and binary upgrades
* [**Managing NGINX Configuration File][4]** – NGINX configuration file structure, the order of directives, directive inheritance rules

## Basic Functionality

* [**Web server][5]** – Configuring virtual servers and locations, using variables, rewriting URIs, and customizing error pages
* [**Serving static content][6]** – Setting the root directory for requested content, and creating ordered lists of files to serve if the original index file or URI does not exist
* [**Reverse proxy][7]** – Proxying requests to HTTP, FastCGI, uwsgi, SCGI, and memcached servers; controlling proxied request headers; and buffering of responses from proxied servers
* [**Compression and decompression][8]** – Compressing responses on the fly to minimize use of network bandwidth
* [**Web content cache][9]** – Caching static and dynamic content from proxied servers

## Managing SSL Traffic

* [**SSL termination][46]** – Delivering web content over HTTPS
* [**SSL termination for TCP upstreams][47]** – Delivering TCP traffic over HTTPS
* [**SSL between NGINX and an HTTP upstream][48]** – Securing HTTP traffic between NGINX and upstream servers
* [**SSL between NGINX and a TCP upstream][49]** – Securing TCP traffic between NGINX and upstream servers

## Load Balancing

* [**HTTP load balancer][10]** – Distributing HTTP requests across a group of servers based on a choice of algorithms, with passive and proactive checking of upstream server health and runtime modification of the load-balancing configuration
* [**TCP and UDP load balancer][11]** – Distributing TCP connections and UDP datagrams across a group of servers based on a choice of algorithms, with passive and proactive checking of upstream server health and runtime modification of the load-balancing configuration
* [**On-the-Fly Configuration][12]** – Add, delete, modify upstream servers on-the-fly with NGINX REST API
* [**Using the PROXY protocol][13]** – Configuring NGINX and NGINX Plus to receive client connection information passed through proxy servers and load balancers such as HAproxy and Amazon Elastic Load Balancer

## Restricting Access

* **[Limiting access to proxied HTTP resources][54]** – Controlling access based on client IP address, limiting the number of simultaneous connections, and limiting request rate and bandwidth per connection
* **[Restricting access with HTTP Basic authentication][55]** – Configuring a username/password authentication for HTTP
* **[Configuring authentication based on subrequest results][56]** – Authenticating each request to your website with an external server or service.
* **[Restricting access by geographical location][57]** – Controlling access based on a client location
* **[Restricting access to proxied TCP resources][58]** – Controlling access based on client IP address, limiting the number of simultaneous connections, and limiting bandwidth per connection
* **[Dynamic IP Address Blacklisting][59]** – Blacklisting IP addresses taken from a dynamically configurable database.

## Logging And Monitoring

* [**HTTP Health Checks][14]** – Passive and proactive checking of HTTP upstream server health
* [**TCP Health Checks][15]** – Checking of TCP upstream server health
* [**UDP Health Checks][16]** – Checking of UDP upstream server health
* [**Live activity monitoring][17]** – Monitoring NGINX Plus status and performance metrics in real time with the live activity monitoring dashboard, using JSON for collecting stats
* [**Logging errors and requests][18]** – Configuring error log and access log, logging to syslog
* **[Debugging NGINX][19]** – Configuring the debugging log, collecting the debugging information, obtaining core dump files

## High Availability

* **[High availability for NGINX Plus][66]** – Configuring high availability of NGINX Plus instances on premises with a solution based on keepalived
* **[Active-active and additional passive nodes][67]** – Improving failover redundancy and scalability by adding additional nodes
* **[High availability for NGINX Plus in AWS][68]** – Configuring high availability of NGINX Plus instances in AWS with a solution based on keepalived and Elastic IP address
* **[Configuration sharing][69]** – Sharing configuration across a cluster of NGINX Plus servers

## Mail Proxy

* **[Configuring NGINX as a mail proxy server][70]** – Enabling the mail proxy server functionality

## NGINX Plus with ModSecurity WAF

NGINX and NGINX Plus also support HTTP/2, proxying of WebSocket traffic, streaming media delivery, and content transformation through SSI or XSLT. All of these features – and more – are covered in detail in the [reference documentation][20].

## Deployment and Migration Guides

* **[Amazon Route 53][21]** – Implementing global server load balancing (GSLB) with Route 53 and NGINX Plus
* **[Apache Tomcat][22]** – Using NGINX and NGINX Plus to load balance Apache TomcatTM application servers
* **[Chef][23]** – High availability of NGINX Plus instances with a solution based on keepalived and Chef
* **[Citrix NetScaler][24]** – Migrating load balancer configuration to NGINX Plus from Citrix NetScaler
* **[F5 BIG‑IP][25]** – Migrating load balancer configuration to NGINX Plus from F5 BIG‑IP
* **[Google Cloud Platform][26]** – Using NGINX Plus in an all-active, highly available load balancing deployment on Google Compute Engine (GCE)
* **[JBoss][27]** – Using NGINX and NGINX Plus to load balance JBoss® application servers (both commercial and open source)
* **[Microsoft Exchange][28]** – Using NGINX Plus to load balance both TCP-based and HTTP-based Microsoft® ExchangeTM traffic
* **[New Relic Plug-In][29]** – Enabling monitoring of NGINX with New Relic APM™
* **[Node.js][30]** – Using NGINX and NGINX Plus to load balance Node.js® application servers
* **[Oracle E-Business Suite][31]** – Using NGINX Plus to load balance Oracle® EBS servers
* **[Oracle WebLogic Server][32]** – Using NGINX Plus to load balance Oracle WebLogic servers
* **[uWSGI and Django][33]** – Using NGINX as an application gateway with uWSGI and Django

## NGINX Plus Releases

* **[Feature Lists for NGINX Plus Releases][88]**

[1]: https://www.nginx.com/products/feature-matrix/ "NGINX and NGINX Plus Feature Matrix"
[2]: https://www.nginx.com#contact-us
[3]: https://www.nginx.com/resources/admin-guide/processes-and-runtime-control/
[4]: https://www.nginx.com/resources/admin-guide/configuration-files/
[5]: https://www.nginx.com/resources/admin-guide/nginx-web-server/
[6]: https://www.nginx.com/resources/admin-guide/serving-static-content/
[7]: https://www.nginx.com/resources/admin-guide/reverse-proxy/
[8]: https://www.nginx.com/resources/admin-guide/compression-and-decompression/
[9]: https://www.nginx.com/resources/admin-guide/content-caching/
[10]: https://www.nginx.com/resources/admin-guide/load-balancer/
[11]: https://www.nginx.com/resources/admin-guide/tcp-load-balancing/
[12]: https://www.nginx.com/resources/admin-guide/load-balancing-api/
[13]: https://www.nginx.com/resources/admin-guide/proxy-protocol/
[14]: https://www.nginx.com/resources/admin-guide/http-health-check/
[15]: https://www.nginx.com/resources/admin-guide/tcp-health-check/
[16]: https://www.nginx.com/resources/admin-guide/udp-health-check/
[17]: https://www.nginx.com/resources/admin-guide/monitoring/
[18]: https://www.nginx.com/resources/admin-guide/logging-and-monitoring/
[19]: https://www.nginx.com/resources/admin-guide/debug/
[20]: http://nginx.org/en/docs/
[21]: https://www.nginx.com/resources/deployment-guides/global-load-balancing-amazon-route-53-nginx-plus/
[22]: https://www.nginx.com/resources/deployment-guides/load-balance-apache-tomcat/
[23]: https://www.nginx.com/blog/nginx-plus-high-availability-chef/
[24]: https://www.nginx.com/resources/deployment-guides/migrating-load-balancer-configuration-netscaler-nginx-plus/
[25]: https://www.nginx.com/resources/deployment-guides/migrating-load-balancer-configuration-f5-nginx-plus/
[26]: https://www.nginx.com/resources/deployment-guides/all-active-nginx-plus-load-balancing-gce/
[27]: https://www.nginx.com/resources/deployment-guides/jboss-application-servers/
[28]: https://www.nginx.com/resources/deployment-guides/exchange-load-balancer-nginx-plus/
[29]: https://www.nginx.com/blog/nginx-plugin-for-new-relic/
[30]: https://www.nginx.com/resources/deployment-guides/load-balance-node-js/
[31]: https://www.nginx.com/resources/deployment-guides/load-balance-oracle-e-business-suite/
[32]: https://www.nginx.com/resources/deployment-guides/oracle-weblogic-server/
[33]: https://www.nginx.com/resources/admin-guide/gateway-uwsgi-django



[34]: https://www.nginx.com/resources/admin-guide/installing-nginx-plus/
[35]: https://www.nginx.com/resources/admin-guide/installing-nginx-open-source/
[36]: https://www.nginx.com/resources/admin-guide/setting-nginx-plus-environment-microsoft-azure/
[37]: https://www.nginx.com/resources/admin-guide/setting-nginx-plus-environment-amazon-ec2/
[38]: https://www.nginx.com/resources/admin-guide/nginx-plus-google-cloud-platform/

[46]: https://www.nginx.com/resources/admin-guide/nginx-ssl-termination/
[47]: https://www.nginx.com/resources/admin-guide/nginx-tcp-ssl-termination/
[48]: https://www.nginx.com/resources/admin-guide/nginx-https-upstreams/
[49]: https://www.nginx.com/resources/admin-guide/nginx-tcp-ssl-upstreams/

[54]: https://www.nginx.com/resources/admin-guide/restricting-access/
[55]: https://www.nginx.com/resources/admin-guide/restricting-access-auth-basic/
[56]: https://www.nginx.com/resources/admin-guide/restricting-access-auth-request/
[57]: https://www.nginx.com/resources/admin-guide/restricting-access-geoip/
[58]: https://www.nginx.com/resources/admin-guide/restricting-access-tcp/
[59]: https://www.nginx.com/resources/admin-guide/ip-blacklisting/

[66]: https://www.nginx.com/resources/admin-guide/nginx-ha-keepalived/
[67]: https://www.nginx.com/resources/admin-guide/nginx-ha-keepalived-nodes/
[68]: https://www.nginx.com/resources/admin-guide/active-passive-ha-aws-elastic-ip-address/
[69]: https://www.nginx.com/resources/admin-guide/configuration-sharing/
[70]: https://www.nginx.com/resources/admin-guide/mail-proxy/

[88]: https://www.nginx.com/resources/admin-guide/nginx-plus-releases/
