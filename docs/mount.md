1. Haga click en **_Services_** y posteriormente seleccione el servicio de [**_EC2_**](https://console.aws.amazon.com/ec2/) el cual se encuentra bajo la categoría de Compute (**_https://console.aws.amazon.com/ec2/_**) .
2. Cambie a la región de **_N. Virginia_** en la esquina superior derecha.
3. Haga click en **_Running instances_**.
4. Seleccione la casilla que se encuentra a lado de la instancia **_Amazon Linux 2 - SGW Lab_**.
5. Haga click en **_Connect_**.
6. Seleccione **_EC2 Instance Connect (browser-based SSH connection)_** y haga click en **_Connect_** para tener acceso a su instancia vía SSH por medio del navegador web.

![Connect (browser-based SSH connection)](images/connect.png)

![EC2 CLI](images/ec2cli.png)


**_*Nota_**. Si por alguna razón no pudo conectarse a la instancia por medio de SSH via el navegador web (500 Server error), intente la opción de A standalone SSH client siguiendo las instrucciones que ahí se indican (terminal para usuarios Mac/Linux, putty para usuarios Windows).

7. Ejecute el siguiente comando para obtener privilegio root:

```
sudo su
```

8. Para montar su file share debe crear un directorio en donde montarlo. Ejecute el siguiente comando:

```
mkdir gateway
```

9. Ejecute el comando que guardó en el editor de texto para montar el file share en Linux sustituyendo **_[MounthPath]_** por **_/home/ec2-user/gateway_**. El comando deberá quedar algo así:

> mount -t nfs -o nolock,hard 172.31.34.218:/file-gateway-lab-su-bucket /home/ec2-user/gateway

10. Dentro de la ruta en el que se encuentra hay un directorio llamado **_baseballdatabank-2019.2_** que contiene archivos .csv con estadísticas de baseball. Ejecute el siguiente comando para copiar estos archivos al file share que acaba de montar:

```
cp -rv /home/ec2-user/baseballdatabank-2019.2/* /home/ec2-user/gateway/
```

12.	Haga click en **_Services_** y después en [**_S3_**](https://console.aws.amazon.com/storagegateway/).
13.	Ingrese al bucket que creó para este laboratorio.
13.	Verifique que los archivos que copió se encuentran en el bucket.
