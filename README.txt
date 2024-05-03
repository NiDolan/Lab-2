���������
 ![Lab-2](Lab-2/Lab-2.png)
# ������� ���������

| ���������� | ��������� | IP-�����     | ����� �������   |
|------------|-----------|--------------|-----------------|
| S1         | VLAN 1    | 192.168.1.11 | 255.255.255.0   |
| S2         | VLAN 1    | 192.168.1.12 | 255.255.255.0   |
| PC-A       | NIC       | 192.168.1.1  | 255.255.255.0   |
| PC-B       | NIC       | 192.168.1.2  | 255.255.255.0   |

## ����� 1. �������� � ��������� ����

- ��������� ����� ��������� � ������������ � ����������.
    ```
    Switch(config)#hostname S1
    Switch(config)#hostname S2
    PC-A
    PC-B
    ```

- ��������� IP-������, ��� ������� � ������� ���������.
    ```
    S1(config)#interface vlan 1
    S1(config-if)#ip address 192.168.1.11 255.255.255.0
    S1(config-if)#no shutdown

    S2(config)#interface vlan 1
    S2(config-if)#ip address 192.168.1.12 255.255.255.0
    S2(config-if)#no shutdown
    ```

- ��������� `cisco` � �������� ������� ������� � VTY.
    ```
    S1(config)#line console 0
    S1(config-line)#password cisco

    S1(config)#line vty 0 4
    S1(config-line)#password cisco

    S2(config)#line console 0
    S2(config-line)#password cisco

    S2(config)#line vty 0 4
    S2(config-line)#password cisco
    ```

- ��������� `class` � �������� ������ ������� � ������������������ ������ EXEC.
    ```
    S1(config)#enable secret class
    S2(config)#enable secret class
    ```

## ����� 2. �������� ������� MAC-������� �����������

- �������� MAC-������ ������� ���������.
    - MAC-����� ���������� PC-A: `00D0.D3E9.1E77`
    - MAC-����� ���������� PC-B: `0090.210E.30C0`
    - MAC-����� ����������� S1 Fast Ethernet 0/1: `0001.96e6.6c01`
    - MAC-����� ����������� S2 Fast Ethernet 0/1: `00e0.f9ab.9301`

- ����������� ������� MAC-������� �����������. ������� �� � ������� MAC-����� �����������? **��, MAC-����� ����������� �������.**

- �������� ������� MAC-������� ����������� S2 � ����� ���������� ������� MAC-�������. ������� �� � ������� MAC-������� ������ ��� VLAN 1? ������� �� ������ MAC-������? **���.**





