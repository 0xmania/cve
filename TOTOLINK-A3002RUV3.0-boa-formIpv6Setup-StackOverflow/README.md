# TOTOLINK A3002RUV3.0 boa formIpv6Setup Stack Overflow

## Proof of Concept

![](./img/1.png)

## Affected Version

A3002RUV3 <= V3.0.0-B20220304.1804

## Vulnerability Description

The TOTOLINK A3002RUV3 (version <= V3.0.0-B20220304.1804) boa service interface does not strictly filter user input. Authenticated attackers can trigger a stack overflow vulnerability by constructing requests with a special format, causing arbitrary code execution or denial of service.

## Vulnerability Analysis

Firmware download address: https://www.totolink.net/home/menu/detail/menu_listtpl/download/id/221/ids/36.html

The `formIpv6Setup` request is as follows: After receiving `static_ipv6`, it directly uses `strcpy`, causing a stack overflow vulnerability.

![](./img/2.png)