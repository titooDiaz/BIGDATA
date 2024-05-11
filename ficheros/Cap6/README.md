<p align="center">
  <img width="150px" src="https://i.ibb.co/bXvzjXm/LOGO-h1.png" />
</p>


# PASOS A SEGUIR PARA INSTALAR PYSPARK EN LINUX
<br>
instalacion de java:
<br>

```linux
sudo apt-get update
```

<br>

```linux
sudo apt-get install default-jdk 
```

<br>

Nos dirigiremos a la pagina ofcial de [spark](https://spark.apache.org/downloads.html)!
<br>
Daremos clic en la tercer opcion:
<br>
![Imagen opcion clic](<3.png>)
<br>
Ahora descargaremos el archivo .tgz
<br>
![Imagen descargar tgz](<tgz.png>)
<br>

Abriremos la carpeta donde se descargo en la terminal
<br>
Ahora vamos a descomprimir el fichero:
<br>

```linux
tar xvzf <nombre del archivo> 
```

<br>
Ahora renombramos la carpeta
<br>

```linux
mv <nombre actual del archivo> spark 
```

<br>
Ahora vamos a agregar al PATH para ejecutar spark desde cualquier lugar
<br>
para eso colocaremos los sigueintes comandos:
<br>

```linux
nano ~/.bash_profile 
```
<br>

Se abrira una interfaz donde deberemo pegar:

<br>

```linux
export SPARK_HOME=/ruta/al/directorio/spark
export PATH=$SPARK_HOME/bin:$PATH 
export PYSPARK_PYTHON=python3 
```

El directorio de la carpeta lo peudes encontrar:

```linux
cd spark
pwd
```
y copiar lo que devulve la consola!

<br>

Donde spark home deberemos cambiarlo por la ubicacion donde se encuentra nuestro archivo spark!

<br>

Cuando hayamos finalizado de agregarar las rutas (paths), cargamos el fichero .profile escribiendo sobre la línea de comando:

<br>

```linux
source ~/.bash_profile 
```

<br>

Finalmente instlaremos su version en python:
<br>

```linux
pip install pyspark 
```

<br>

Abriremos una nueva terminal para comprobar que su instalacion fue exitosa:
<br>

```linux
pyspark 
```

<br>

RESULTADO:
<br>
![alt text](<resultado.png>)
