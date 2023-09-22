# Jarkom-Modul-1-I10-2023
Praktikum Jaringan Komputer Modul 1 I10
Computer Network Practicum 1st Module I10

| Name                        | NRP        |
|-----------------------------|------------|
|Riski Ilyas                  | 5025211189 |
|Vija Wildan Gita Prabawa     | 5025211261 |

## Flag 1
```
a. Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut? 
b. Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut? 
c. Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
d. Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
```
![no1(2)](https://github.com/riskiilyas/testtttt/assets/71499142/c5e7ad57-ee47-4975-a549-660d4c8aed5e)
![no1](https://github.com/riskiilyas/testtttt/assets/71499142/90ccdcce-8571-4e14-9ed8-a09ef1c5f206)
To answer this question, we need to sort the packets by protocol first, then look for packets with the FTP protocol. Once we find those, we should search for the packet where the user begins uploading a file, typically marked by the "STOR" command. Once we have identified this packet, we can examine the Transmission Control Protocol (TCP) section to find the "seq raw" and "ack" values. To find the response, we can look for the response packet that follows the request packet.

## Flag 2
```
Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!
```
![no2](https://github.com/riskiilyas/testtttt/assets/71499142/4afe8275-9c96-4b3e-aeec-a5d6cb5d2445)
To find the web server used by a Computer Network web page, we can examine packets with the HTTP protocol type. Then, from all those packets, we can directly look at the packet that represents the server's response. In this example, we can see packet 1916, which contains an OK/200 response. Then, we just need to inspect the data within that packet, and in the data, it's evident that the web server being used is `gunicorn`.

## Flag 3
```
a. Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?
b. Protokol layer transport apa yang digunakan?
```
![no3](https://github.com/riskiilyas/testtttt/assets/71499142/28eae7dc-e492-437b-b169-a3ef0917c3e2)
To answer this question, we need to perform a filter query as shown below:
```
(ip.addr == 239.255.255.250 && udp.port == 3702) || (ip.dst == 239.255.255.250 && udp.port == 3702)
```

## Flag 4
```
Berapa nilai checksum yang didapat dari header pada paket nomor 130?
```
![no4](https://github.com/riskiilyas/testtttt/assets/71499142/99219d43-d01d-4614-9970-ae01db9be252)
To find the checksum in packet 130, first, we need to go to the "Go" menu, then select "Go To Packet," and enter 130 to navigate to packet 130. Consequently, we can view its checksum in the "User Datagram Protocol" section. In this case, the checksum value is found to be `0x18e5`.

## Flag 5
```
Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.
- Berapa banyak packet yang berhasil di capture dari file pcap tersebut?
- Port berapakah pada server yang digunakan untuk service SMTP?
- Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?
```
To answer the question, we need to extract the zip file first by exporting the object to EMF. By exporting it, it will reveal the password that encoded in Base64.
![no5](https://media.discordapp.net/attachments/919468862725046322/1154755442094907473/image.png?width=1121&height=702)
After we decoded the password, we can put it into the zip file and got the text file that consist of the netcat. From that we can start answer the question

To answer the first question, we only need to find out how much packet that captured in the .pcap file.
![no5a](https://media.discordapp.net/attachments/919468862725046322/1154758209240846376/image.png?width=1440&height=376)

For the second question, we need to find what port used for SMTP.
![no5b](https://media.discordapp.net/attachments/919468862725046322/1154757709380452463/image.png?width=1125&height=702)

And the third question is that we need to find out which one is the public IP. Public IP doesn't start with 10.xxx.xxx.xx or 192.xxx.xxx.xxx so we can find it easily.
![no5c](https://media.discordapp.net/attachments/919468862725046322/1154757766926319696/image.png?width=531&height=35)

## Flag 7
```
Berapa jumlah packet yang menuju IP 184.87.193.88?
```
![Screenshot 2023-09-22 183133](https://github.com/riskiilyas/testtttt/assets/71499142/082e40d2-9b6f-4045-b8d1-36231848417e)
To answer this question, we need to perform a filter query as shown below:
```
ip.dst  == 184.87.193.88
```

## Flag 8
Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)

## Flag 9
```
Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!
```
![Screenshot 2023-09-22 184028](https://github.com/riskiilyas/testtttt/assets/71499142/f90e86eb-58ca-49f9-9d74-ae7281a6b978)

To answer this question, we need to perform a filter query as shown below:
```
ip.src == 10.51.40.1 && ip.dst != 10.39.55.34
```


## FLag 10
Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet
