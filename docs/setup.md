Antes de comenzar, debe asegurarse de estar trabajando en la región de N. Virgina. Esto lo puede verificar en el menú desplegable que se encuentra en la esquina superior derecha de la consola de AWS.

 
1.	Creación de key pair.

Lo primero que debe hacer es crear un key pair. Este key pair le permitirá acceder a la instancia que creará más adelante y la cual migrará a otra región de AWS utilizando CloudEndure. Para crear un key pair debe hacer lo siguiente:

1.	Haga click en Services y posteriormente seleccione el servicio de EC2 el cual se encuentra bajo la categoría de Compute.
2.	Una vez en EC2, haga click en la sección de Key Pairs que se encuentra en el menú de la izquierda y posteriormente haga click en Create key pair.
3.	En el campo de Key pair name ingrese un nombre para su key pair (ejemplo: sgw).
4.	Haga click en Create y guarde el archivo que se va a descargar.


2.	Desplegar plantilla de CloudFormation

A continuación, va a desplegar una instancia de Linux en la región de N. Virgina utilizando una plantilla de CloudFormation. Esta plantilla se hará cargo de instalar la instancia, aplicar las actualizaciones de sistema operativo correspondientes, instalar el servidor web Apache y configurar un security group con los puertos 22 (ssh) y 80 (http) habilitados. Esta instancia es la que va a migrar utilizando CloudEndure. Para desplegar dicha plantilla siga los siguientes pasos:

1.	Haga click en Services y después en CloudFormation que se encuentra bajo la categoría de Management & Governance (también puede teclear CloudFormation en el campo de búsqueda).
2.	Haga click en Create stack.
3.	En el campo de Amazon S3 URL ingrese la siguiente URL: 
https://awsimmersiondays.s3.amazonaws.com/sgw-lab.yaml
4.	Haga click en Next.
5.	En el campo de Stack name escriba StorageGatewayLab.
6.	En el menú desplegable de KeyPair bajo la sección de Parameters elija el key pair que creó anteriormente (sgw).
7.	Haga click en Next.
8.	En la siguiente pantalla haga click de nuevo en Next.
9.	En la siguiente pantalla haga click en Create stack.
10.	Espere unos minutos a que el status de lanzamiento de la plantilla indique CREATE_COMPLETE.
11.	Una vez que el lanzamiento haya sido completado, haga click en la sección de Outputs y copie los valores EC2InstancePublicIp y StorageGatewayPublicIp. Guarde estas IPs en un editor de texto ya que las utilizará más adelante.
