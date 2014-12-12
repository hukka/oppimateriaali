Tietoverkot
===========
IPv4, DNS, DHCP, SSL/TLS, SMTP, HTTP

IP ei välttämättä ole sama kone,
vaan se riippuu siitä minne liikenne ohjataan.
Esimerkiksi Netflixillä saattaa olla kone operaattorin verkossa.

Kansainväliset tietoverkot, ja miksi kaivuri voi katkaista Elisan,
ja miten jotkut sivut toimivat mutta toiset eivät samaan aikaan.

DDOS, tahallinen ja tahaton (slashdotting).

Mitä tapahtuu kun pyydät nettiselainta avaamaan sivun?
------------------------------------------------------
::

    > route
    Kernel IP routing table
    Destination     Gateway         Genmask         Flags Metric Ref    Use Iface
    default         OpenWrt.lan     0.0.0.0         UG    0      0        0 eth1

> dig f.root-servers.net  +showsearch +trace
;; Received 913 bytes from 127.0.1.1#53(127.0.1.1) in 255 ms
;; Received 734 bytes from 192.5.5.241#53(f.root-servers.net) in 71 ms
;; Received 660 bytes from 192.43.172.30#53(i.gtld-servers.net) in 51 ms
;; Received 156 bytes from 216.239.36.10#53(ns3.google.com) in 20 ms
Googlen IP osoite on siis esimerkiksi 80.239.229.250.

::

    > traceroute 80.239.229.250
    traceroute to 80.239.229.250 (80.239.229.250), 30 hops max, 60 byte packets
     1  OpenWrt.lan (192.168.1.1)  1.434 ms  1.572 ms  1.906 ms
     2  dsl-espbrasgw1-54f9c0-1.dhcp.inet.fi (84.249.192.1)  2.226 ms  2.352 ms  2.932 ms
     3  hls-b2-link.telia.net (62.115.143.50)  3.830 ms  4.287 ms hls-b1-link.telia.net (62.115.143.84)  4.543 ms
     4  google-ic-154333-hls-b2.c.telia.net (80.239.195.206)  4.855 ms hls-b2-link.telia.net (80.91.252.159)  5.135 ms hls-b2-link.telia.net (213.155.134.58)  5.514 ms
     5  google-ic-154333-hls-b2.c.telia.net (80.239.195.206)  5.845 ms * *
     6  * * *



::

    > nc 80.239.229.250 80
    GET / HTTP/1.1
    Host: google.com

::

    HTTP/1.1 302 Found
    Cache-Control: private
    Content-Type: text/html; charset=UTF-8
    Location: http://www.google.fi/?gfe_rd=cr&ei=k9qJVKuLA8HO-ga264CYCA
    Content-Length: 258
    Date: Thu, 11 Dec 2014 17:55:31 GMT
    Server: GFE/2.0
    Alternate-Protocol: 80:quic,p=0.002

    <HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
    <TITLE>302 Moved</TITLE></HEAD><BODY>
    <H1>302 Moved</H1>
    The document has moved
    <A HREF="http://www.google.fi/?gfe_rd=cr&amp;ei=k9qJVKuLA8HO-ga264CYCA">here</A>.
    </BODY></HTML>

www.google.com on 173.194.40.255

::

    > traceroute 173.194.40.255
    traceroute to 173.194.40.255 (173.194.40.255), 30 hops max, 60 byte packets
     1  OpenWrt.lan (192.168.1.1)  7.798 ms  14.358 ms  19.065 ms
     2  dsl-espbrasgw1-54f9c0-1.dhcp.inet.fi (84.249.192.1)  23.126 ms  27.840 ms  37.507 ms
     3  hls-b1-link.telia.net (62.115.143.84)  38.288 ms hls-b2-link.telia.net (62.115.143.50)  38.073 ms hls-b1-link.telia.net (62.115.143.84)  50.594 ms
     4  s-bb3-link.telia.net (80.91.245.136)  51.148 ms s-bb4-link.telia.net (213.155.133.78)  51.239 ms s-bb4-link.telia.net (80.91.245.36)  55.539 ms
     5  s-b5-link.telia.net (213.155.133.19)  58.176 ms s-b5-link.telia.net (62.115.141.203)  80.825 ms s-b5-link.telia.net (62.115.141.199)  84.247 ms
     6  google-ic-306509-s-b5.c.telia.net (62.115.45.14)  88.733 ms  13.966 ms  13.204 ms
     7  209.85.250.192 (209.85.250.192)  13.623 ms  15.627 ms  16.861 ms
     8  209.85.253.151 (209.85.253.151)  19.255 ms  19.378 ms  16.971 ms
     9  arn02s06-in-f31.1e100.net (173.194.40.255)  20.003 ms  19.852 ms  20.101 ms

::

    > nc 173.194.40.255 80
    GET /?gfe_rd=cr&amp;ei=k9qJVKuLA8HO-ga264CYCA HTTP/1.1
    Host: www.google.fi

paljon dataa.
