### ssh

## Configuracion SSH en Windows. 
1. creamos una carpeta oculta `./llaves-ssh ` en `C` para guardar las llaves ssh.
```
cd /c/
mkdir .claves-ssh
``` 
2. Ejecutamos el comando 
`ssh-keygen -t rsa -C "fitopaisa@hotmail.com"`
El correo tiene que ser con el que nos registramos en github.
cuando pida la ruta ponemos `/c/.claves-ssh/github_rsa`
dejamos frase y contraseña vacios para que nos pida contraseña. 
```
ssh-keygen -t rsa -C "fitopaisa@hotmail.com
/c/.claves-ssh/github_rsa

```

3. Para configurar ssh en una ruta especifica 
usamos ssh-agent en segundo plano con `eval "$(ssh-agent -s)"`
```
$ eval "$(ssh-agent -s)""
$ ssh-add /c/ruta-ssh/github_rsa
```
4. Agregamos la llave ssh ejecutando `ssh-add /c/.claves-ssh/github_rsa`

## Codigo completo
```
cd /c/
mkdir .claves-ssh
ssh-keygen -t rsa -C "fitopaisa@hotmail.com
/c/.claves-ssh/github_rsa
$ eval "$(ssh-agent -s)""
$ ssh-add /c/ruta-ssh/github_rsa

```
