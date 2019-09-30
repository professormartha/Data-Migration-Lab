1. Cambie a la región de **_Ohio_** en la esquina superior derecha de la consola de AWS.
2. Haga click en **_Services_** y posteriormente seleccione el servicio de [**_S3_**](https://s3.console.aws.amazon.com/) el cual se encuentra bajo la categoría de **_Storage_** (**_https://s3.console.aws.amazon.com/_**).
3. Haga click en **_+ Create bucket_**.
4. Ingrese un nombre para su bucket en **_Bucket name_** con la siguiente nomenclatura: **_file-gateway-lab-su-nombre_** (ejemplo: **_file-gateway-lab-mariano-rivera_**).
5. Haga click en **_Create_**.
6. Guarde el nombre de su bucket en un editor de texto ya que lo utilizará más tarde.
7.Haga click en **_Services_** y después en [**_Storage Gateway_**](https://console.aws.amazon.com/storagegateway/) que se encuentra bajo la categoría de **_Storage_** (**_https://console.aws.amazon.com/storagegateway/_**).
8. Cambie a la región de **_N. Virginia_** en la esquina superior derecha de la consola de AWS.
9. . Haga click en **_File Shares_** en el menú lateral del lado izquierdo.
10. Haga click en **_Create file share_**.
11. En el campo de **_Amazon S3 bucket name_** ingrese el nombre del bucket de S3 que creó anteriormente.
12. En el menú desplegable de **_Gateway_** seleccione el Gateway que creó anteriormente.
13. Haga click en **_Next_**.
14. En la pantalla de **_Configure how files are stored in Amazon S3_** haga click en **_Next_** (usará los valores predeterminados).
15. En la pantalla de **_Review_** haga click en **_Create file share_**.
16. Haga click en **_File Shares_** en el menú lateral del lado izquierdo.
17. Seleccione la casilla del share que acaba de crear.
18. Copie las instrucciones para conectarse a su file share desde una máquina **_Linux_** y guárdelas en un editor de texto ya que las utilizará más adelante.

![Outputs](images/onlinux.png)