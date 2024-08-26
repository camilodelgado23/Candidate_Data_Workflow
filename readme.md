# workshop1 

## Por: Camilo Jose Delgado Bolaños - 2225337 

En este workshop se recibió un dataset con candidatos a la espera de ser contratados. Dichos datos fueron migrados a una base de datos relacional (MySQL), se les realizó un E.D.A. con el objetivo de entender y comprender el contenido de los mismos, y se realizaron modificaciones en base a ello. Finalmente, se desarrollaron visualizaciones de datos sobre el contenido del dataset

## Herramientas Usadas 

- Python: 
    - Python Scripting: Para automatizar tareas como la inserción de datos en bases de datos, y la exportación de archivos.
    - Visual Studio Code (VS Code): Como entorno para escribir y ejecutar código Python.
    - Jupyter Notebook: Para desarrollo interactivo de código, exploración de datos, y ejecución de scripts.
    - Virtual Environment (venv): Para gestionar dependencias y aislar el entorno de desarrollo.

- MySQL:
    - MySQL Workbench: Para gestión y administración de bases de datos MySQL, incluyendo la ejecución de consultas SQL.

- Git: Para control de versiones y seguimiento de cambios en el proyecto.
- GitHub: Para alojar el repositorio del proyecto, gestionar el control de versiones, y colaborar en el desarrollo del proyecto.
- Power BI: Para la visualizacion de Datos

## Estructura del Repositorio 

La estructura del repositorio es la siguiente 

- **Análisis_de_Datos:** Carpeta Donde tendremos los archivos donde se realizaran el análisis del dataset y sacaremos el dataset transformado con el que se realizaran las visualizaciones de datos
    - **candidates_analisis.ipynb:** En este notebook se lleva acabo el E.D.A del dataset de candidates original para ver que tanto tiene el dataset y poder sacar diversas conclusiones y modificaciones
    - **candidates_transformado.ipynb:** En este notebook filtraremos el dataset original donde solo dejaremos la información de los empleados contratados, y donde además agregaremos una nueva columna de ID para poder identificar a cada uno de los candidatos con mayor facilidad
- **Base_de_Datos_Operaciones**: En esta carpeta tendremos las operaciones que realizamos en nuestra Base de Datos en este caso MySQL, como lo es realizar la conexión a la BD, y la creación de las tablas donde insertaremos nuestro dataset
    - **carga_dataset_BD.ipynb:** En este notebook insertamos los 2 dataset tanto el original como el transformado y los insertamos en nuestra Base de Datos
    - **conexionBD.py:** En este archivo tenemos el script que con ayuda de la libreria MySQL nos conectamos a la Base de Datos de MySQL
    - **tablasBD.ipynb:** En este notebook  creamos las tablas donde crearemos las tablas de  los 2 dataset en la Base de Datos, el original y el transformado
- **csv:** Carpeta donde almacenaremos nuestros archivos .csv ****
    - **candidates_contratados.csv:** Dataset transformado con solo los  candidatos contratados y con una columna extra de ID que facilita la identificación de los candidatos
    - **candidates.csv:** Dataset original de las solicitudes de los candidatos
- **.gitignore:** Archivo en donde colocamos los archivos que no queremos que se suban a nuestro repositorio de git hub como lo es nuestro entorno virtual o nuestro archivo en donde almacenamos las credenciales
- **readme.txt:** Archivo donde colocaremos una breve descripción de nuestro proyecto y donde se explica como ejecutar el workshop
- **requirements.txt:** Archivo en donde colocamos las librerías/bibliotecas que usamos en nuestro entorno para el desarrollo del workshop
- **Dashboard_workshop1.pdf**: Archivo PDF en donde se muestran las visualizaciones de los datos

## Instrucciones para la ejecucion 

### Requerimientos 

- Python: https://www.python.org/downloads/
- MySQL: https://dev.mysql.com/downloads/mysql/
- PowerBI: https://www.microsoft.com/es-es/download/details.aspx?id=58494
- MySQL Workbench(Opcional): https://dev.mysql.com/downloads/workbench/

Clonamos el repositorio en nuestro entorno 

```bash
  git clone https://github.com/camilodelgado23/workshop__1.git
```
Vamos al repositorio clonado 

```bash
  cd workshop1
```
Instalamos el entrono virtual  donde vamos a trabajar 

```bash
  Python -m venv venv 
```
Iniciamos el entorno 

```bash
  .\venv\Scripts\Activate
```
Instalamos las librerias necesarias almacenadas en el archivo requirements.txt

```bash
  pip install -r requirements.txt
```
Creamos la Base de Datos en MySQL 

```bash
  CREATE SCHEMA workshop1;
```
Creamos el archivo credentials.py donde almacenaremos las credenciales para conectarnos a la Base de Datos, puede seguir la siguiente estructura 

```bash
  DB_HOST = 'localhost'
  DB_USER = 'root'
  DB_PASSWORD = 'root'
  DB_NAME = 'workshop1'
```
Podemos probar si las credenciales son correctas ejecutando nuestro archivo conexion.py.

Para una correcta ejecucion de nuestro repositorio ejecutamos primero nuestro notebook tablasBD, donde crearemos las tablas en la base de datos. Despues ejecutamos el notebook carga_dataset_BD donde cargamos los 2 datasets a las tablas ya creadas en la BD. 

Podemos ejecutar los otros 2 notebooks que son candidates_analisis, y candidates_transformado, en donde realizamos el E.D.A del dataset original y el proceso donde transformamos el dataset original  

Para realizar las visualizaciones de datos tenemos que conectar la Base de Datos MySQL al PowerBI para esto seguimos los siguientes pasos: 

Nos vamos a PowerBI y lo iniciamos, nos vamos a la pantalla de inicio y le damos a obtener datos donde buscaremos la opción de Base de datos MySQL 

![Texto alternativo](imagenes\1.png)

Nos toca descargar un conector nos dirigimos al siguiente enlace y lo descargamos

Descargar conector: https://dev.mysql.com/downloads/connector/net/

![Texto alternativo](imagenes\1.png)

Ingresamos el nombre del servidor y el de nuestra Base de datos 

![Texto alternativo](imagenes\2.1.png)

Seleccionamos Base de datos y Colocamos nuestro usuario y contraseña 

![Texto alternativo](imagenes\2.png)

Finalmente seleccionamos las tablas que vamos a usar en este caso usaremos la de candidates_contratados 

![Texto alternativo](imagenes\3.png)
