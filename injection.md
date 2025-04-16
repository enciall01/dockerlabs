
## Primero debemos iniciar la maquina
```
bash auto_deploy.sh injection.tar
```
[![parrot-2024-09-09-14-36-53.png](https://i.postimg.cc/fL5vY4Tj/parrot-2024-09-09-14-36-53.png)](https://postimg.cc/7GG7yWzf)
## vemos la ip despues usaremos PING para cpmprobar si la maquina esta encendida
[![parrot-2024-09-09-14-37-29.png](https://i.postimg.cc/k5zggsSJ/parrot-2024-09-09-14-37-29.png)](https://postimg.cc/gwyWMv4Q)
## vemos que tenemos respuesta entonces usaremos nmap para verificar si tenemos puertos abiertos
[![parrot-2024-09-09-14-39-54.png](https://i.postimg.cc/XJx3ygGB/parrot-2024-09-09-14-39-54.png)](https://postimg.cc/k6VL0Ky7)
## vemos que tenemos un puerto 22 y 80 abierto si buscamos la ip en el navegador vemos esto
[![parrot-2024-09-09-14-40-34.png](https://i.postimg.cc/k5GXFzCF/parrot-2024-09-09-14-40-34.png)](https://postimg.cc/ns8JndCC)
## podemos usar una vulnerabilidad llamada SQL injection lo que haremos es poner ' or 1=1-- -  te recomendaria ver este video de El Pingüino de Mario sobre sql injection link:https://youtu.be/qLeeLRn9Z78?si=0cgRksYDmqQAomZ-``
[![parrot-2024-09-09-14-41-00.png](https://i.postimg.cc/zfH4NY1f/parrot-2024-09-09-14-41-00.png)](https://postimg.cc/8FDZd3c8)
### le damos enter y vemos esto
[![parrot-2024-09-09-14-41-11.png](https://i.postimg.cc/m2bYW3Gz/parrot-2024-09-09-14-41-11.png)](https://postimg.cc/PNRpmwJT)
## nos da un usuario y su contraseña recuerdas el puerto ssh si problamos las credenciales vemos que podemos acceder
[![parrot-2024-09-09-16-22-51.png](https://i.postimg.cc/wBGSNT9H/parrot-2024-09-09-16-22-51.png)](https://postimg.cc/Tyn7MxyH)
### vemos que las credenciales son validas asi que haremos una escalada de privilegios con binarios
[![parrot-2024-09-09-14-44-19.png](https://i.postimg.cc/vmYP31Qf/parrot-2024-09-09-14-44-19.png)](https://postimg.cc/CR2HKxnx)
## vemos env asi que usaremos este comando para elevar privilegios 
[![parrot-2024-09-09-14-48-15.png](https://i.postimg.cc/XvBg29RZ/parrot-2024-09-09-14-48-15.png)](https://postimg.cc/wtHJMRTH)
