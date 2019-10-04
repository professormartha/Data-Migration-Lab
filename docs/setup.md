Lo primero que debe hacer es crear un key pair. Este key pair le permitirá acceder a la instancia que creará más adelante y a la cual le mostrará el file share que creará con el servicio de Storage Gateway.

1. Asegúrese de estar trabajando en la región de **_N. Virgina_**. Esto lo puede verificar en el menú desplegable que se encuentra en la esquina superior derecha de la consola de AWS.
2. Haga click en **_Services_** y posteriormente seleccione el servicio de [**_EC2_**](https://console.aws.amazon.com/ec2/) el cual se encuentra bajo la categoría de **_Compute_** - **_https://console.aws.amazon.com/ec2/_**.
3. Una vez en EC2, haga click en la sección de **_Key Pairs_** que se encuentra en el menú de la izquierda.
5. Haga click en **_Create key pair_**.

![Create Key Pair](images/keypair.png)

6. En el campo de **_Key pair name_** ingrese un nombre para su key pair (ejemplo: **_sgw_**).
7. Haga click en **_Create_** y guarde el archivo que se va a descargar.

A continuación, va a desplegar una plantilla de CloudFormation. Esta plantilla deplegará una instancia de Linux Amazon 2 con su grupo de seguridad correspondiente con el puerto 22 habilitado (ssh). En esta instancia usted montará un file share que creará utilizando el servicio de Storage Gateway. Esta plantilla también desplegará una segunda instancia de EC2, que es la que usted configurará como Storage gateway, y creará el grupo de seguridad necesario con los servicios de HTTP, NFS y SMB habilitados.

8. Haga click en **_Services_** y después en [**_CloudFormation_**](https://console.aws.amazon.com/cloudformation/) que se encuentra bajo la categoría de **_Management & Governance_** (también puede teclear CloudFormation en el campo de búsqueda) - **_https://console.aws.amazon.com/cloudformation/_**.
9. Haga click en **_Create stack_**.
10.	En el campo de **_Amazon S3 URL_** ingrese la siguiente URL: 
>http://storage-gateway.oldschool.cloud/sgw-lab.yaml
11.	Haga click en **_Next_**.
12.	En el campo de **_Stack name_** escriba **_StorageGatewayLab_**.
13.	En el menú desplegable de **_KeyPair_** bajo la sección de **_Parameters_** elija el key pair que creó anteriormente (**_sgw_**).
14.	Haga click en **_Next_**.
14.	En la siguiente pantalla haga click de nuevo en **_Next_**.
16.	En la siguiente pantalla haga click en **_Create stack_**.
17.	Espere unos minutos a que el status de lanzamiento de la plantilla indique **_CREATE_COMPLETE_**.
18.	Una vez que el despliegue de la plantilla haya sido completado, haga click en la sección de **_Outputs_** y copie los valores **_EC2InstancePublicIp_** y **_StorageGatewayPublicIp_**. Guarde estas IPs en un editor de texto ya que las utilizará más adelante.

![Outputs](images/outputs.png)