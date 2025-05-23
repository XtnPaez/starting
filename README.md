# Guía para conectar GitHub con SSH en Windows y clonar repositorios

En git bash

```
git config --global user.name "Tu Nombre"
git config --global user.email "tuemail@ejemplo.com"
```

Luego, para conectarse, vamos a sacar una key

```
ssh-keygen -t ed25519 -C "tuemail@ejemplo.com"
```

Copias la clave pública con

```
cat ~/.ssh/id_ed25519.pub
```

Y generas una nueva key en https://github.com/settings/keys

Ponerle el proxy a git

git config --global http.proxy http://eproxy.cncps.gob.ar:8080
git config --global https.proxy http://eproxy.cncps.gob.ar:8080

En Visual Studio Code, instalar Github Pul Request : abajo a la derecha conectarlo con el repo

Clonar el repo

```
git clone https://github.com/XtnPaez/fiscalizar.git
```

