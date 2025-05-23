# Guía para conectar GitHub con SSH en Windows y clonar repositorios

1. Instalar Git

Descargar Git para Windows en https://git-scm.com/download/win

Ejecutar el instalador y aceptar opciones por defecto.

2. Abrir la consola

Usar Git Bash para todos los comandos Git (buscar "Git Bash" en Windows).

También podés usar la terminal integrada de Visual Studio Code.

3. Generar clave SSH (una por PC)

En Git Bash:

Verificar si ya existe una clave:
    ls ~/.ssh/id_rsa.pub

Si no existe, crear nueva:
    ssh-keygen -t ed25519 -C "tu_email@example.com"

(Reemplazá por tu email de GitHub. Aceptá ubicación por defecto y frase de paso opcional)

Iniciar el agente SSH:
    eval $(ssh-agent -s)

Añadir la clave generada:
    ssh-add ~/.ssh/id_ed25519

Copiar la clave pública para GitHub:
    cat ~/.ssh/id_ed25519.pub

Ir a https://github.com > Settings > SSH and GPG keys > New SSH key

Pegar la clave pública y guardar con un título identificador para la PC.

4. Clonar repositorio usando SSH

En Git Bash, navegar a la carpeta donde querés clonar el repo, por ejemplo:
    cd C:/Users/TuUsuario/Proyectos

Copiar URL SSH del repo en GitHub (botón Code > SSH), y clonar:
    git clone git@github.com:usuario/repositorio.git

5. Verificar a qué repositorio estás conectado

Abrir la carpeta clonada en Visual Studio Code

Abrir la terminal integrada (Terminal > New Terminal)

Ejecutar:
    git remote -v

Verás la URL del repositorio remoto configurado.

6. Uso en varias PCs

Repetir los pasos para generar y agregar la clave SSH en cada PC.

Clonar el repo en cada PC para tener la copia local.

Usar Git Bash o la terminal de VS Code para trabajar con Git.

Usar comandos estándar de Git (git add, git commit, git push) para subir cambios.
