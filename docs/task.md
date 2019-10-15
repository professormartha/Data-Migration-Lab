Una vez que su agente ha sido creado, debe crear una tarea de migración (task) en donde definirá el origen y destino de los datos que va a migrar.

10. Haga clck en **_Tasks_** en el menú lateral de la izquierda.
11. Haga click en **_Create task_**.
12. En **_Location_** type seleccione **_Network File System (NFS)_**.
13. En **_Agents_** seleccione el agente de DataSync que acaba de crear.
14. En **_NFS Server_** ingrese la IP de **_NFSInstancePublicIP_** que guardó en el editor de texto.
15. En **_Mount path_** ingrese la siguiente ruta:

```
/mnt/nfs
```

16. Haga click en **_Next_**.
17. En **_Location type_** seleccione **_Amazon S3 bucket_**.
18. En **_S3 bucket_** seleccione el bucket que creó anteriormente.
19. En **_IAM role_** haga click en **_Autogenerate_** para generar un rol que permita a DataSync interactur con su bucket.
20. Haga click en **_Next_**.
21. En la siguiente pantalla deje los valores predeterminados y haga click en **_Next_**.
22. Haga click en **_Create task_**.
23. Haga clck en **_Tasks_** en el menú lateral de la izquierda. Podrá ver que el status de la tarea es **_Creating_**.

![Creating task](images/taskcreating.png)

24. Espere unos minutos a que el status de la tarea cambie a **_Available_** y proceda al siguiente módulo.

![Task available](images/taskavailable.png)