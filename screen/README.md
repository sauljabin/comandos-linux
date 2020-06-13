# Comando **screen**

- Para iniciar sesion screen

```bash
screen
```
- Crear sesion con nombre

```bash
screen -S session_name
```

- Crear una nueva ventana  desde consola

```bash
Ctrl+a c
```
### Lista de comandos para trabajar con Ventanas de screen Linux
- `Ctrl+a c` Crea una nueva Ventana de consola
- `Ctrl+a`  " Lista todas las Ventanas
- `Ctrl+a 0` Cambia de Ventanas desde 0 (Por numero)
- `Ctrl+a A` Renombra la ventana actual
- `Ctrl+a S` Separa la region actual horizontal en dos regiones
- `Ctrl+a |` Separa la region actual vertical en dos regiones
- `Ctrl+a tab` Cambia el foco actual por la siguiente region.
- `Ctrl+a Ctrl+a` Conmuta entre la region actual y la anterior
- `Ctrl+a Q` Cerrar todas las regiones excepto la actual.
- `Ctrl+a X` Cierra la region actual.

### Desconectar de la sesion de screen

Puede desconectarse de la sesión de pantalla en cualquier momento escribiendo:

`Ctrl+a d`

El programa que se ejecuta en la sesión de pantalla continuará ejecutándose después de que se desconecte de la sesión.

### Volver a conectar a una sesion de screen

Para reanudar su sesión de screen, use el siguiente comando:

```bash
screen -r
```

En caso de tener multiples sesiones de screen corriendo, necesitas agregar el ID de la session despues de `r`.

Para encontrar el ID de sesión, enumere las sesiones de screen actuales con:

```bash
screen -sl
```

```bash
There are screens on:
    10835.pts-0.linuxize-desktop   (Detached)
    10366.pts-0.linuxize-desktop   (Detached)
2 Sockets in /run/screens/S-linuxize.
```

Si quieres restaurar el sesion screen 10835.pts-0, entonces escribe:

```bash
screen -r 10835
```

## Personaliza screen
Cuando `screen` inicia, este lee su configuracion de parametros desde `/etc/screenrc` and `~/.screenrc` si el archivo está presente. Podemos modificarlo de acuerdo a nuestras preferencias.

Aquí hay una muestra de configuración `~/.screenrc` con línea de estado personalizada y algunas opciones adicionales:

`~/.screenrc`:

```bash
 # Turn off the welcome message
startup_message off

# Disable visual bell
vbell off

# Set scrollback buffer to 10000
defscrollback 10000

# Customize the status line
hardstatus alwayslastline
hardstatus string '%{= kG}[ %{G}%H %{g}][%= %{= kw}%?%-Lw%?%{r}(%{W}%n*%f%t%?(%u)%?%{r})%{w}%?%+Lw%?%?%= %{g}][%{B} %m-%d %{W}%c %{g}]'
```

## Uso basico de screen
A continuación se detallan los pasos más básicos para comenzar con `screen`:

1. En la consola escriba `screen`.
2. Corra el programa deseado.
3. Use la secuencia de teclas: `Ctrl+a` y luego `Ctrl+d` para desprenderse de la sesión de  `screen`.
4. Vuelva a la sesión de pantalla escribiendo: `screen -r`.