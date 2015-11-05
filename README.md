# sctrld
Netflow v5 Collector

## �������� sctrld ## 

 ���� Netflow v5 ������ �������� IP � ���������� ������ ��� ���������� ������
 
## ��������� ����� �������� sctrld.config ##

 NetflowAdress  - ip � ���� �� ������ ������� netflow. ������: "0.0.0.0:2055"
 NetflowBufferSize - ��� ����� ���,
  WebPort - ���� �� ������� �������� WEB ������. ������: "8080"
 CmdDown - ������� ��� ���������� ������. %s - IP ������ ������ "speed-set %s 0.5"
 CmdUp - ������� ��� ���������� ������. %s - IP ������ ������ "speed-set %s 100"

## �������� API ##
������   | �������� | ������   | �����
-------- | -------- | -------- | --------
v1/set/  | �������� IP ��� ������� � ��������� ����� ������� | http://localhost:8080/v1/set/?ip=172.16.0.1&limit=200&offstart=1&offstop=2 | {"ip": "172.16.0.1", "stat": 0, "limit": 200, "offstart": 1, "offstop": 2}
v1/add/ | ��������� ����� ��� IP ������ �� �������� | http://localhost:8080/v1/add/?ip=172.16.0.1&limit=100 | {"ip": "172.16.0.1", "limit_add": 100}
v1/get/ | �������� ���������� �� IP ������ | http://localhost:8080/v1/get/?ip=172.16.0.1 | {"ip": "172.16.0.1", "stat": 0, "limit": 300, "offstart": 1, "offstop": 2}
runtime/ | ������� ���������� �� ����������. | http://localhost:8080/runtime/  | {"Memheap": 917504, "Memidle": 393216, "Meminuse": 524288, "goroutines": 7, "NextGC:": 4194304, "PauseTotalNs": 0}

��������� | �������� | ������
-------- | --------  | --------
ip | ip ����� | 172.16.0.2
limit | ����� ������� ��� ip ������ | 1000 - 1000 byte
offstart | ��� � �������� �� ������� ������ | 1, ������ ������ � 1.00 ����� �������� �� �����
offstop | ��� �� �������� �� ������� ������ | 2, ������ ������ � 2.00 ����� ����� �������� 
   

