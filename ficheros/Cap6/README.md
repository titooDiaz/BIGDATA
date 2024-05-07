<p align="center">
  <img width="150px" src="https://i.ibb.co/bXvzjXm/LOGO-h1.png" />
</p>

> [!NOTE]
> *** PASOS A SEGUIR PARA INSTALAR PYSPARK EN LINUX ***
> instalacion de java:
> ` sudo apt-get update `
> ` sudo apt-get install default-jdk `
> 
> Nos dirigiremos a la pagina ofcial de [spark](https://spark.apache.org/downloads.html)!
> Daremos clic en la tercer opcion:
> ![Imagen opcion clic](<3.png>)
>
> Ahora descargaremos el archivo .tgz
> ![Imagen descargar tgz](<tgz.png>)
>
> Abriremos la carpeta donde se descargo en la terminal
> Ahora vamos a descomprimir el fichero:
> ` tar xvzf <nombre del archivo> `
> Ahora renombramos la carpeta
> ` mv <nombre actual del archivo> spark `
> Ahora vamos a agregar al PATH para ejecutar spark desde cualquier lugar
> para eso colocaremos los sigueintes comandos:
> ` cd spark `
>
> ` nano ~/.bash_profile `
> Se abrira una interfaz donde deberemo pegar:
> ``` export SPARK_HOME=/ruta/al/directorio/spark ```
> ``` export PATH=$SPARK_HOME/bin:$PATH ```
> ``` export PYSPARK_PYTHON=python3 ```
> Donde spark home deberemos cambiarlo por la ubicacion donde se encuentra nuestro archivo spark!
> 
> Finalmente instlaremos su version en python:
> ` pip install pyspark `
> Abriremos una nueva terminal para comprobar que su instalacion fue exitosa:
> ` pyspark `
