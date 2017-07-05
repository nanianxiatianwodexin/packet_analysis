# 功能

* 读取pcap包，打印详细的icmp/tcp/udp协议

* 读取pcap包或网络接口，打印详细的tcp会话数据



# 安装依赖包

 `pip install -r requirements.txt`


* [pynids](https://github.com/MITRECND/pynids.git)

   * mac

   `brew install libnids`

   * linux

   `sudo apt-get install libnet1-dev libpcap-dev`

   `git clone https://github.com/MITRECND/pynids.git`

   `cd pynids`

   `sudo python setup.py build`

   `sudo python setup.py install`

* [dpkt](http://dpkt.readthedocs.io/en/latest/index.html)

   `pip install dpkt`

   或者

   `git clone https://github.com/kbandla/dpkt.git`


# 使用
* 读取pcap包，打印详细的icmp/tcp/udp协议

    `python print_pcap.py --help`

    `python print_pcap.py --pcapfile=data/pcap_pub/http_gzip.pcap  --assetport=80`

    数据示例



    [TCP]	[1099056060.4	2004-10-29 13:21:00]	192.168.69.2:34059(00:0a:95:67:49:3c) ----->192.168.69.1:80(00:c0:f0:2d:4a:a3)	SEQ=2415239731	ACK=2518192935	FLAGS=['ACK', 'PSH']	WIN=46	DATA=GET /test/ethereal.html HTTP/1.1
    Host: cerberus
    User-Agent: Mozilla/5.0 (X11; U; Linux ppc; rv:1.7.3) Gecko/20041004 Firefox/0.10.1
    Accept: text/xml,application/xml,application/xhtml+xml,text/html;q=0.9,text/plain;q=0.8,image/png,*/*;q=0.5
    Accept-Language: en-us,en;q=0.5
    Accept-Encoding: gzip,deflate
    Accept-Charset: ISO-8859-1,utf-8;q=0.7,*;q=0.7
    Keep-Alive: 300
    Connection: keep-alive
    Cookie: FGNCLIID=05c04axp1yaqynldtcdiwis0ag1

    ttl=64




* 读取pcap包或网络接口，打印详细的tcp会话数据

   第一步:指定配置
   [server.yaml](etc/server.yaml)


   第二步:
   `python print_tcp_session.py`
   

   数据示例


    [addr]: 192.168.69.2:34059 192.168.69.1:80

    [ts_start]: 1099027260.4 2004-10-29 13:21:00

    [ts_end]: 1099027260.43 2004-10-29 13:21:00

    [Data_Client_To_Server]:

    GET /test/ethereal.html HTTP/1.1

    Host: cerberus

    User-Agent: Mozilla/5.0 (X11; U; Linux ppc; rv:1.7.3) Gecko/20041004 Firefox/0.10.1

    Accept: text/xml,application/xml,application/xhtml+xml,text/html;q=0.9,text/plain;q=0.8,image/png,*/*;q=0.5

    Accept-Language: en-us,en;q=0.5

    Accept-Encoding: gzip,deflate

    Accept-Charset: ISO-8859-1,utf-8;q=0.7,*;q=0.7

    Keep-Alive: 300

    Connection: keep-alive

    Cookie: FGNCLIID=05c04axp1yaqynldtcdiwis0ag1



    [Data_Server_To_Client]:

    HTTP/1.1 200 OK

    Date: Fri, 29 Oct 2004 05:21:00 GMT

    Server: Apache/2.0.50 (Fedora)

    Last-Modified: Fri, 29 Oct 2004 05:20:21 GMT

    ETag: "126e1f-6d-371b2f40"

    Accept-Ranges: bytes

    Vary: Accept-Encoding

    Content-Encoding: gzip

    Content-Length: 92

    Connection: close

    Content-Type: text/html; charset=UTF-8


    �      ��(�ͱ��HML���)�,�I�s-�H-JM�Qp�H�-�IUHLO�чHr��CT�$�T5qbU4L� �l	 �nCm   




