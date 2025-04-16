### 1. Iniciamos la maquina con este comando

[![iniciar.png](https://i.postimg.cc/7Zb92qYj/iniciar.png)](https://postimg.cc/v4F5RFnv)

### 2. Usamos PING para comprobar si tenemos conctividad con la maquina

[![ping.png](https://i.postimg.cc/tCG76kRb/ping.png)](https://postimg.cc/WtS2LMJY)

###3. Ahora usamos NMAP para saber si la maquina tiene puertos abiertos

[![nmap.png](https://i.postimg.cc/L5wtk1s7/nmap.png)](https://postimg.cc/FkbkN13g)


### vemos que aparece el puerto 80 http
### 4. Buscamos la direccion ip en el navegador

[![web.png](https://i.postimg.cc/gkwbHXsK/web.png)](https://postimg.cc/2Vftz5Pq)


### vemos que nos pide subir un archivo 
### 5. En el navegador buscamos Reverse Shell Generator

[![Reverse-Shell.png](https://i.postimg.cc/8kYM09dV/Reverse-Shell.png)](https://postimg.cc/CdjRZv6v)

### 6. Ponemos los parametros correctos 
[![parametros.png](https://i.postimg.cc/W3gzYYss/parametros.png)](https://postimg.cc/bDYqsTG5)

### en ip ponemos nuestra ip que lo puedes ver con hostname -I o (en algunas distribuciones) ifconfig en port ponemos 8080 y buscamos PHP PentestMonkey

[![ip.png](https://i.postimg.cc/zXnMDCG3/ip.png)](https://postimg.cc/N5jbprTw)

### creamos un achivo reverse.php

[![nc.png](https://i.postimg.cc/Y9L57TPm/nc.png)](https://postimg.cc/0MxWdXP8)


[![nano.png](https://i.postimg.cc/BvrhTbhX/nano.png)](https://postimg.cc/1gKcPm1Q)

### 7.Subimos el archivo PHP

[![subirphp.png](https://i.postimg.cc/pryWb0H9/subirphp.png)](https://postimg.cc/kR33WvD9)

### 8. comunmente los archivos que guardamos de guardan en uploads

[![uploads.png](https://i.postimg.cc/fLNCrFYK/uploads.png)](https://postimg.cc/06V76VWM)

### 9.vemos que el archivo php esta ahi, antes de darle click 

[![webpp.png](https://i.postimg.cc/kg7fsLFv/webpp.png)](https://postimg.cc/KRsPvqW1)

### 10.Volvemos ala terminal y usamos netcat para ponernos en escucha por el puerto previamente establecido en la reverse shell 

[![c.png](https://i.postimg.cc/28tS7ffP/c.png)](https://postimg.cc/D8qh7H0g)

### 11. Ahora le damos click al archivo php

[![nw.png](https://i.postimg.cc/C5Qn8BN2/nw.png)](https://postimg.cc/xNLdDdBG)

### ahora tenemos control de la maquina

### 12. Despues escribimos este comando para la tti operativa porque muestra un resultado incorrecto

[![Virtual-Box-Debian-19-07-2024-17-14-45.png](https://i.postimg.cc/g2DXyTNR/Virtual-Box-Debian-19-07-2024-17-14-45.png)](https://postimg.cc/5XX2bncN)

### 13. Usamos sudo -l para verificar que podemos ejecutar

[![Virtual-Box-Debian-19-07-2024-17-15-56.png](https://i.postimg.cc/cCHXZ3Ck/Virtual-Box-Debian-19-07-2024-17-15-56.png)](https://postimg.cc/ZBGrxCr6)

### nos da un binario env

### 14. Vamos a la pagina GTFOBins y buscamos el binario

[![Virtual-Box-Debian-19-07-2024-17-16-56.png](https://i.postimg.cc/3JjZy70F/Virtual-Box-Debian-19-07-2024-17-16-56.png)](https://postimg.cc/dL1CXbBh)

### encontramos este comando 

[![Virtual-Box-Debian-19-07-2024-17-17-25.png](https://i.postimg.cc/q7GfQWFs/Virtual-Box-Debian-19-07-2024-17-17-25.png)](https://postimg.cc/Ff1nHCNz)

### 15. Regresamos ala terminal y ponemos:

[![Virtual-Box-Debian-19-07-2024-17-18-11.png](https://i.postimg.cc/Hxz4n9h4/Virtual-Box-Debian-19-07-2024-17-18-11.png)](https://postimg.cc/47KhFVZm)

### Y ahora felicidades ya eres root


