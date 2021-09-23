# Instalación de Maven en el SO
### Repositorio dedicado a la documentación de la instalación de OpenJdk en Ubuntu

Para poder instalar Maven en Ubuntu debemos seguir una serie de pasos sencillos ingresando los comandos adecuados en la terminal. Pero antes de instalar el programa, debemos actualizar el índice del paquete con “sudo apt update”.


 <p align="center">
<img width=55% src="https://i.imgur.com/Nvrmt0Q.png">
 </p>
 
 
Tal y como se ve en la captura de pantalla, ingresé el comando con el que actualicé el índice del paquete y después ingresé el comando “sudo apt install maven” para instalar el programa.
 
 
 <p align="center">
<img width=55% src="https://i.imgur.com/otM9pEf.png">
 </p>
 
Al finalizar, comprobé su versión usando “mvn -version”, con lo que confirmé que la instalación había sido exitosa. 

Sin embargo, tal y como lo había hecho, se instaló una versión predeterminada del programa, ligeramente anterior a la última versión actual. Para usar la versión más moderna, debía seguir otra serie de pasos que se describen a continuación. 

 
  <p align="center">
<img width=55% src="https://i.imgur.com/Vbctq21.png">
 </p>
 
 Primero, tal y como se puede apreciar, descargué Apache Maven en el directorio “/tmp”, para que, una vez finalizada la descarga, pudiera extraer el archivo en el directorio “/opt”.

Justo después, usando “sudo  ln -s /opt/apache-maven-3.8.2 /opt/maven” creé un enlace simbólico con el que adquirir un mayor control sobre las versiones y actualizaciones de Maven, ya que cuando se lanza una nueva versión, se puede actualizar la instalación cambiando el enlace simbólico. 

 
  <p align="center">
<img width=55% src="https://i.imgur.com/KISTK52.png">
 </p>
 
 Lo que sigue son las variables de entorno: abrimos un archivo en el directorio “/etc/profile.d”, copiamos el código que se muestra a continuación y lo guardamos. 

“export
JAVA_HOME=/usr/lib/jvm/IMPORTANTE-RESPETAR-LA-VERSION-DE-JAVA-INSTALADA
export M2_HOME=/opt/maven
export MAVEN_HOME=/opt/maven
export PATH=${M2_HOME}/bin:${PATH}”

  <p align="center">
<img width=55% src="https://i.imgur.com/ImjrbDZ.png">
 </p>
 
 A continuación hacemos que el script sea ejecutable usando el comando “sudo chmod +x /etc/profile.d/maven.sh” y, haciendo uso del otro comando “ source /etc/profile.d/maven.sh” cargamos las variables de entorno. 
 
 <p align="center">
<img width=55% src="https://i.imgur.com/fOnBbp2.png">
 </p>
 
 Una vez hecho, ya solo nos quedaría un paso: comprobar una vez más la instalación de Maven usando “mvn -version”. El resultado debería ser el siguiente:
 
  <p align="center">
<img width=55% src="https://i.imgur.com/SqwGaDr.png">
 </p>
 
 Si todo está correcto, ya se puede empezar a utilizar Maven en el SO. 
