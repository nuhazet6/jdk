# Instalación de JDK en Ubuntu

## 1.Instalar Java:
Primero hay que actualizar el sistema:
```sudo apt-get update```
Segundo se instala Java:
```sudo apt-get install default-jdk```
Comprobamos que lo tenemos instalado con lo siguiente:
```java --version```

## 2.Instalar los JDK

Para instalar Ubuntu Java Open JDK ("la que utilizaremos en 1º").
 - OpenJDK:
   - 11
   ```
   sudo apt install openjdk-11-jdk
   ```
    - 9
   ```
   sudo apt install openjdk-9-jdk
   ```
    - 8
   ```
   sudo apt install openjdk-8-jdk
   ```
 Mostraremos la 8 Para ello verificaremos la versión de java que se esta ejecutando con la sentencia:

```console
  java --version
```
En caso que no se ejecuta la versión 8 se debe configurar las variables de entorno.

## Configuración de las variables de entorno

 El siguiente paso consiste en establecer  las variables de entorno. Es necesario porque cuando se usa Java, Linux necesita saber dónde está ubicado el programa para ejecutarlo y qué versión de Java usar de forma predeterminada. Para modificar esto, usaremos el editor de texto nano. Primero, abra el archivo en Nano.

### Listar la versiones de OpenJDK instaladas

 Ejecuta el siguiente comando para verificar que se han descargado las diferentes versiones de OpenJDK.

```console
 ls /usr/lib/jvm
```

### Actualización de las variables de entorno

 Edita y modifica el fichero profile, con los comandos:

```console sudo update-alternatives --config java```
 y selecciona la version _8_, cuyo valor es __java-1.8.0-openjdk-amd64__.

 Otra opción es : añadir el siguiente código:

```console
# Java version
JAVA_HOME=/usr/lib/jvm/_____openJdk_____
PATH=$PATH:$HOME/bin:$JAVA_HOME/bin
export JAVA_HOME
export JRE_HOME
export PATH
```

 en

```console
/etc/profile.d/java.sh
```
Haga que el script sea ejecutable con chmod:

```console
sudo chmod +x /etc/profile.d/java.sh
```

Finalmente, cargue las variables de entorno usando el comando de source

```console
source /etc/profile.d/java.sh
```
