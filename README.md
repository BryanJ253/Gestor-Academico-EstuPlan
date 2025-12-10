# Gestor-Academico-EstuPlan
En este repositorio se publica el proyecto para el curso de Programación De Computadores, el cual consiste en un Gestor Academico dirigido a los estudiantes de la Universidad Nacional de la Facultade de Ingenieria. Es una aplicacion de escritorio que ayuda a gestionar la vida universitaria del estudiante, compilando distintas herramientas para que sean de facil acceso para el estudiandete e implementando apis de Google Calendar y Google Classroom para gestionar tareas horarios entre otras cosas.
## Requerimientos 
## 1.Instalación del entorno
A continuación, se describen los pasos para instalar y ejecutar la aplicación en un entorno local utilizando Python.
### 1.1 Descarga del proyecto
Descargue o copie el proyecto en una carpeta de su preferencia, por ejemplo:


C:\Users\[[USUARIO]]\Documents\[[Gestor Academico]] en Windows.


Asegúrese de que los archivos principales estén presentes, entre ellos:


inicio_app.py


Login.py


google_calendar.py


google_classroom.py


otros archivos auxiliares, imágenes, etc.


### 1.2 Instalación de Python
Descargue Python desde la página oficial:


 https://www.python.org/downloads/



Durante la instalación en Windows, marque la opción:


"Add Python to PATH" (Agregar Python al PATH).


Finalice la instalación.


Para verificar la instalación:
Abra Símbolo del sistema o PowerShell y ejecute:


python --version

Debería mostrar una versión igual o superior a 3.10.

## 2. Creación de entorno virtual e instalación de dependencias
Es recomendable usar un entorno virtual para aislar las dependencias del proyecto.
### 2.1 Creación del entorno virtual (Windows)
Abra PowerShell o CMD en la carpeta del proyecto [Gestor Academico].


Ejecute:


python -m venv venv

Active el entorno virtual:


.\venv\Scripts\Activate.ps1

Si tiene problemas de ejecución de scripts en PowerShell, puede que necesite modificar la política de ejecución.


### 2.2 Instalación de librerías necesarias (pip)
Con el entorno virtual activado, instale las librerías utilizadas por el proyecto.
Para ejecutar la app con los avances del classroom es necesario instalar el pillow con este comando:
pip install pillow

Otro comando que vas a necesitar es para instalar el matplotlib
pip install matplotlib

Para usar el inicio de sesión de google se necesita instalar lo siguiente:
pip install google-auth google-auth-oauthlib requests pyrebase4 pillow
Instalar tambien setuptools python.exe -m pip install setuptools
Instalar estas dependencias:
pip install pdf2image
Toca instalar customtkinter
py -3.14 -m pip install customtkinter
tocar instalar firebaseadmin
py -3.14 -m pip install firebase-admin




## 3. Librerías utilizadas y su función
A continuación se listan las librerías principales utilizadas en la aplicación y su propósito:
### 3.1 Librerías estándar de Python
tkinter y ttk
 Permiten crear la interfaz gráfica de usuario: ventanas, botones, etiquetas, menús, etc.


datetime y calendar
 Se utilizan para manejar fechas, horas y cálculos relacionados con eventos y calendario.


os, os.path
 Manejo de rutas de archivos, comprobación de existencia de archivos, etc.


subprocess
 Permite ejecutar otros programas (en caso de uso puntual para abrir archivos o procesos externos).


math
 Funciones matemáticas generales (si se requieren cálculos específicos).


webbrowser
 Abre enlaces en el navegador web predeterminado (por ejemplo, para abrir páginas de Google Classroom o ayuda externa).


### 3.2 Librerías externas (instaladas con pip)
Pillow (PIL)
 Manejo de imágenes (por ejemplo, iconos, logos de la app, etc.).


google-auth, google-auth-oauthlib, google-api-python-client
 Conjunto de librerías para autenticarse con Google y consumir APIs de Google.


google_auth_oauthlib.flow.InstalledAppFlow se utiliza para el flujo OAuth 2.0 (ventana de login de Google).


googleapiclient.discovery.build para crear servicios de API (Google Calendar, Google Classroom).



## 4. Configuración de credenciales de Google
Para permitir que la aplicación acceda a Google Calendar y Google Classroom, es necesario contar con un archivo de credenciales y autorizar la aplicación en la cuenta de Google del usuario.
### 4.1 Obtención del archivo credentials.json
Ingrese a Google Cloud Console:


 https://console.cloud.google.com/



Cree un proyecto (si aún no tiene uno) o utilice uno existente.


Habilite las APIs necesarias:


Google Calendar API


Google Classroom API


En la sección de Credenciales, cree un ID de cliente OAuth 2.0 de tipo Aplicación de escritorio.


Descargue el archivo de credenciales (credentials.json).


Coloque el archivo credentials.json en la carpeta principal del proyecto  o en la ruta esperada por tu código (ejemplo: mismo directorio donde se encuentra inicio_app.py).


### 4.2 Archivos token.json
La primera vez que se ejecute la aplicación y se intente acceder a Google, se abrirá una ventana en el navegador pidiendo permiso de acceso.


Una vez concedido el permiso, se generará un archivo token.json que contiene el token de acceso.


Este archivo permite que no sea necesario iniciar sesión cada vez que se usa la aplicación (salvo que el token expire o se revoque).


Nota: No comparta credentials.json ni token.json con otras personas. Son archivos sensibles.

## Ejecucion de la aplicacion
A continuacion se mostrara graficamente como es el funcionamiento de nuestra aplicacion, donde se mostrara cada una de las ventanas que esta contiene.
### Login
Esta ventana nos permite ingresar a la aplicacion, confirmando las credenciales que se almacenan en Firebase, en caso de no estar registrados los datos del usuario en firebase, esto se puede realizar con el boton "Crear Cuenta" para registrar el usuario, ademas se puede ingresar sesion con Google para obtener los permisos de las APIS de Google Calendar y Classroom. Una vez se verifiquen las credenciales, la ventana se cerrara y dirigira al usuario a la pestaña principal de la aplicacion donde se encuentran las funcionalidades, y las demas ventanas que se mostraran a continuacion. 


<img width="1002" height="682" alt="image" src="https://github.com/user-attachments/assets/e97a7048-811a-4ea7-a975-a8d4096da2eb" />

### Inicio
En esta ventana se muestran mensajes rapidos de informacion al usuario para que las pueda consultar apenas ingresa a la aplicacion y pueda dar un vistazo general a lo que contiene la aplicacion, donde podra navegar entre las otras ventanas de esta.

<img width="1365" height="729" alt="image" src="https://github.com/user-attachments/assets/9f26bd8e-3736-4c57-9a59-020b818bede9" />

### Calendario
Esta ventana nos permite ver eventos que tengamos en los proximos dias ademas de poder crear eventos o tareas para tenerlas presentes y que no se olviden. Esta ventana involucra la API de Google Calendar, para poder crear los eventos ver las tareas proximas, etc.

<img width="1365" height="732" alt="image" src="https://github.com/user-attachments/assets/558ededb-f76f-4fa6-8572-afbad2a0c9f3" />

### Tareas
Esta ventana permite al usuario vincular su cuenta de Goolge Classroom para obtener los datos que se almacenan en esta, asi poderlos mostrar en la aplicacion, es por eso que en esta ventana se muestran los distintos cursos que tenga inscrito el usuario en Clasroom, y muestra las publicaciones que se realicen, mostrando la informacion detallada del anuncio, tarea o evento.

<img width="1365" height="729" alt="image" src="https://github.com/user-attachments/assets/e820eacd-90a4-4dde-ba65-a73d500a2738" />

### Avance
En esta ventana el usuario podra consultar los distintos pensums de la Facultad de Ingeniería, por lo que buscando su carrera y dando un click, se le redireccionara a la malla curricular de su carrera, para que asi pueda estar al tanto de su avance en la misma y de las materias que podra ver el siguiente semestre.

<img width="1365" height="730" alt="image" src="https://github.com/user-attachments/assets/6cce0ffa-3546-4a71-9210-a585eee9b177" />

### Extensiones
Esta pestaña contiene distintos links, de diversas paginas que le seran utiles al estudiante para gestionar su vida academico, estoa ventana es importante ya que da facil acceso al usuario a las diversas paginas que puede necesitar a lo largo de su vida Academica.

<img width="1365" height="727" alt="image" src="https://github.com/user-attachments/assets/302e389c-c245-4bc9-ae39-c31901d310d9" />


