# Nomad PoC

## Installed software versions

  - Ubuntu 20.04 LTS
  - Nomad 0.11.3
  - Consul 1.74.4
  - LXD 4.2

## Description

All services are run at LXC containers under CentOS 7.8.

```sh
root@nomad:~# lxc list
+-----------+---------+-----------------------+------+-----------+-----------+
|   NAME    |  STATE  |         IPV4          | IPV6 |   TYPE    | SNAPSHOTS |
+-----------+---------+-----------------------+------+-----------+-----------+
| consul-s1 | RUNNING | 10.145.180.83 (eth0)  |      | CONTAINER | 0         |
+-----------+---------+-----------------------+------+-----------+-----------+
| consul-s2 | RUNNING | 10.145.180.48 (eth0)  |      | CONTAINER | 0         |
+-----------+---------+-----------------------+------+-----------+-----------+
| consul-s3 | RUNNING | 10.145.180.254 (eth0) |      | CONTAINER | 0         |
+-----------+---------+-----------------------+------+-----------+-----------+
| nomad-c1  | RUNNING | 172.17.0.1 (docker0)  |      | CONTAINER | 0         |
|           |         | 10.145.180.43 (eth0)  |      |           |           |
+-----------+---------+-----------------------+------+-----------+-----------+
| nomad-c2  | RUNNING | 172.17.0.1 (docker0)  |      | CONTAINER | 0         |
|           |         | 10.145.180.160 (eth0) |      |           |           |
+-----------+---------+-----------------------+------+-----------+-----------+
| nomad-c3  | RUNNING | 172.17.0.1 (docker0)  |      | CONTAINER | 0         |
|           |         | 10.145.180.188 (eth0) |      |           |           |
+-----------+---------+-----------------------+------+-----------+-----------+
| nomad-s1  | RUNNING | 10.145.180.170 (eth0) |      | CONTAINER | 0         |
+-----------+---------+-----------------------+------+-----------+-----------+
| nomad-s2  | RUNNING | 10.145.180.157 (eth0) |      | CONTAINER | 0         |
+-----------+---------+-----------------------+------+-----------+-----------+
| nomad-s3  | RUNNING | 10.145.180.37 (eth0)  |      | CONTAINER | 0         |
+-----------+---------+-----------------------+------+-----------+-----------+
```

LXC containers configured via terraform are located at a root home inside terraform/lxd directory.

## Port Forwarding

 |  Address  |   Port  | Service  |
 |  ------   | ------  | ------   |
 | 127.0.0.1 |  4646  | Nomad UI  |
 | 127.0.0.1 |  8500  | Consul UI |

UI confired via nginx that installed at host VM.
