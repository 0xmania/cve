# TOTOLINK A3002RUV3.0 boa formMapDelDevice Command Injection

## Proof of Concept

![](./img/2.png)

## Affected Version

A3002RUV3 <= V3.0.0-B20220304.1804

## Vulnerability Description

The TOTOLINK A3002RUV3 (version <= V3.0.0-B20220304.1804) boa service interface does not strictly filter user input. Authenticated attackers can trigger a command injection vulnerability by constructing requests with a special format, causing arbitrary system command execution.

## Vulnerability Analysis

Firmware download address: https://www.totolink.net/home/menu/detail/menu_listtpl/download/id/221/ids/36.html

The `formMapDelDevice` request is as follows: After receiving `macstr` and `bandstr`, it uses `sprintf` to concatenate commands without checking, and executes them with `system`, causing a command injection vulnerability.

![](./img/1.png)