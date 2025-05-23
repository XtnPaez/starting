# Guía para conectarse a GitHub desde diferentes PCs

Este documento explica paso a paso cómo conectarte a GitHub desde distintas computadoras, clonar repositorios y verificar a cuál estás conectado desde la consola (por ejemplo, en Visual Studio Code).

## Requisitos

Antes de empezar, asegurate de tener instalados:

- Git: https://git-scm.com/
- Visual Studio Code: https://code.visualstudio.com/
- Una cuenta activa en GitHub: https://github.com/

## 1. Conectarse por primera vez a GitHub

### 1.1 Configurar tu nombre y correo (una sola vez por PC)

    git config --global user.name "Tu Nombre"
    git config --global user.email "tu@email.com"

Usá el mismo correo que tenés registrado en GitHub.

### 1.2 Crear y agregar una clave SSH (opcional pero recomendado)

#### Ver si ya tenés una clave SSH

    ls -al ~/.ssh

#### Si no tenés, generá una nueva clave

    ssh-keygen -t ed25519 -C "tu@email.com"

Presioná Enter para aceptar la ubicación por defecto. Podés dejar la contraseña vacía si lo preferís.

#### Agregar la clave al agente SSH

    eval "$(ssh-agent -s)"
    ssh-add ~/.ssh/id_ed25519

#### Copiar la clave pública

    cat ~/.ssh/id_ed25519.pub

Copiá la salida completa de ese comando.

#### Agregar la clave a GitHub

1. Iniciá sesión en https://github.com/
2. Ir a Settings > SSH and GPG keys
3. Hacer clic en "New SSH key"
4. Pegar la clave copiada, asignarle un nombre y guardar

## 2. Clonar un repositorio en tu PC

Desde el repositorio en GitHub:

1. Hacer clic en el botón "Code"
2. Elegir la opción SSH y copiar la URL (por ejemplo: git@github.com:usuario/repositorio.git)

En la terminal:

    git clone git@github.com:usuario/repositorio.git

Esto descargará el repositorio en una carpeta local.

## 3. Ver a qué repositorio remoto estás conectado

Ingresá al directorio del repositorio:

    cd ruta/del/repositorio

Y ejecutá:

    git remote -v

Esto mostrará algo como:

    origin  git@github.com:usuario/repositorio.git (fetch)
    origin  git@github.com:usuario/repositorio.git (push)

Esto indica la URL del repositorio remoto con el que estás trabajando.

## Recomendaciones para usar múltiples PCs

- Podés repetir este proceso en cada nueva PC.
- Usá la misma cuenta de GitHub en todas las máquinas.
- Si preferís evitar claves SSH, podés usar HTTPS, pero GitHub te pedirá usuario y token personal cada vez.
- Si ya tenés una clave SSH en una PC, podés copiarla a otra (tené cuidado y nunca compartas claves privadas públicamente).

## Consultas

Podés abrir un issue en este repositorio o escribir a tu equipo de desarrollo para soporte.
