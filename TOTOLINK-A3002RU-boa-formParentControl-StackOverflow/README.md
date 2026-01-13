# TOTOLINK A3002RU boa formParentControl Stack Overflow

## Proof of Concept

![](./img/2.png)

## Affected Version

A3002RUV2 <= V2.1.1-B20211108.1455

## Vulnerability Description

The TOTOLINK A3002RU boa service interface does not strictly filter user input. Authenticated attackers can trigger a stack overflow vulnerability by constructing requests with a special format, potentially hijacking pointers or causing arbitrary code execution.

## Vulnerability Analysis

The `formParentControl` request is as follows: After receiving `deviceName`, it directly uses `strcpy`, causing a stack overflow vulnerability.

![](./img/1.png)