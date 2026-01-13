# TOTOLINK A3002RU boa formPortFw Stack Overflow

## Proof of Concept

![](./img/1.png)

## Affected Version

A3002RUV2 <= V2.1.1-B20211108.1455

## Vulnerability Description

The TOTOLINK A3002RU boa service interface does not strictly filter user input. Authenticated attackers can trigger a stack overflow vulnerability by constructing requests with a special format, causing arbitrary code execution.

## Vulnerability Analysis

The `formPortFw` request is as follows: After receiving `service_type`, it directly uses `strcpy`, causing a stack overflow vulnerability.

![](./img/2.png)