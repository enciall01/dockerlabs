### Escaneo inicial con Nmap

```
nmap -p- --open -sS -sC -sV --min-rate 5000 -n -Pn 172.17.0.2
```

[![nmap.png](https://i.postimg.cc/HxX7XF8K/nmap.png)](https://postimg.cc/hz4jqyrb)
### Si vemos el puerto 80 vemos esto

[![webblanco.png](https://i.postimg.cc/WpQSgPFN/webblanco.png)](https://postimg.cc/w3QhYZQZ)
vemos una web en blanco pero si hacemos Ctrl+u para inspeccionar la web vemos un mensaje en comentario
[![ctrlu.png](https://i.postimg.cc/sgtZ0Vzx/ctrlu.png)](https://postimg.cc/75n65rfr)
vemos dos usuarios **juan** y **camilo** los agregamos a un archivo txt llamado users despues hacemos un ataque de fuerza bruta con **medusa**
```
medusa -U users.txt -P /usr/share/wordlists/rockyou.txt -h 172.17.0.2 -M ssh
```
[![medusa.png](https://i.postimg.cc/KvYxVznN/medusa.png)](https://postimg.cc/9zs6wcgR)
vemos que la contraseña de **camilo** es **password1** entramos a ssh con las credenciales 
[![sshlog.png](https://i.postimg.cc/T1j858MC/sshlog.png)](https://postimg.cc/tngv8Mgx)

exploramos por el sistema y encontramos esto
[![correo.png](https://i.postimg.cc/k4XRpCwt/correo.png)](https://postimg.cc/zL6fy9sJ)
antes explorando vimos el usuario de juan si probamos la contraseña con su usuario vemos que podemos acceder
[![juansu.png](https://i.postimg.cc/9FqbpPDH/juansu.png)](https://postimg.cc/CzSbMqCc)
ahora somos juan si hacemos un sudo -l vemos los permisos que tiene juan

```
sudo -l
```

[![sudo-l.png](https://i.postimg.cc/zGGnQnBf/sudo-l.png)](https://postimg.cc/6yF224Cs)
vemos que podemos ejecutar con permisos de root ruby asi que vamos a elevar privilegios
```
sudo ruby -e 'exec "/bin/sh"'
```
[![root.png](https://i.postimg.cc/50VyhV3m/root.png)](https://postimg.cc/Z9wJNXX9)
ahora somos root
