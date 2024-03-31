Creación de un área de trabajo de Azure Machine Learning
Para usar Azure Machine Learning, debe aprovisionar un área de trabajo de Azure Machine Learning en la suscripción de Azure. A continuación, podrá usar Azure Machine Learning Studio para trabajar con los recursos del área de trabajo.

Sugerencia: Si ya tiene un área de trabajo de Azure Machine Learning, puede usarla y pasar a la siguiente tarea.

Inicie sesión en Azure Portal con sus credenciales de Microsoft.https://portal.azure.com
![image](https://github.com/JoseEmmanuelVG/Microsoft_Student_Technical_Training_MLSA-JEVG/assets/89156254/7d284816-7e5b-4122-83ff-421c033d3339)
![image](https://github.com/JoseEmmanuelVG/Microsoft_Student_Technical_Training_MLSA-JEVG/assets/89156254/141aff35-1a00-44de-9133-5bc57bc3819c)
![image](https://github.com/JoseEmmanuelVG/Microsoft_Student_Technical_Training_MLSA-JEVG/assets/89156254/e3755aad-b983-40d6-bc82-e6ce948bf0d7)

Seleccione + Crear un recurso, busque Machine Learning y cree un nuevo recurso de Azure Machine Learning con la siguiente configuración:
Suscripción: su suscripción de Azure.
Grupo de recursos: cree o seleccione un grupo de recursos.
![image](https://github.com/JoseEmmanuelVG/Microsoft_Student_Technical_Training_MLSA-JEVG/assets/89156254/3318a4b1-7af6-4779-8b67-c79af5573858)

Nombre: escriba un nombre único para el espacio de trabajo.
Región: seleccione la región geográfica más cercana.
Cuenta de almacenamiento: tenga en cuenta la nueva cuenta de almacenamiento predeterminada que se creará para el área de trabajo.
Almacén de claves: tenga en cuenta el nuevo almacén de claves predeterminado que se creará para el área de trabajo.
Application Insights: tenga en cuenta el nuevo recurso de Application Insights predeterminado que se creará para el área de trabajo.
Registro de contenedor: Ninguno (se creará uno automáticamente la primera vez que implemente un modelo en un contenedor).
![image](https://github.com/JoseEmmanuelVG/Microsoft_Student_Technical_Training_MLSA-JEVG/assets/89156254/3415d721-546d-43ef-a8cc-3729e758ff46)

Seleccione Revisar + crear y, a continuación, seleccione Crear. Espere a que se cree el área de trabajo (puede tardar unos minutos) y, a continuación, vaya al recurso implementado.

Seleccione Launch Studio (o abra una nueva pestaña del explorador, vaya a https://ml.azure.com e inicie sesión en Azure Machine Learning Studio con su cuenta de Microsoft). Cierre todos los mensajes que se muestran.

En Azure Machine Learning Studio, debería ver el área de trabajo recién creada. Si no es así, seleccione Todas las áreas de trabajo en el menú de la izquierda y, a continuación, seleccione el área de trabajo que acaba de crear.
![image](https://github.com/JoseEmmanuelVG/Microsoft_Student_Technical_Training_MLSA-JEVG/assets/89156254/fc20fc1d-7eab-496e-8bc3-dc7c5ae589bd)




![alt text](image-1.png)

Uso del aprendizaje automático automatizado para entrenar un modelo
El aprendizaje automático automatizado le permite probar varios algoritmos y parámetros para entrenar varios modelos e identificar el mejor para sus datos. En este ejercicio, utilizará un conjunto de datos de detalles históricos de alquiler de bicicletas para entrenar un modelo que prediga el número de alquileres de bicicletas que se deben esperar en un día determinado, en función de las características estacionales y meteorológicas.

Cita: Los datos utilizados en este ejercicio se derivan de Capital Bikeshare y se utilizan de acuerdo con el acuerdo de licencia de datos publicado.

En Azure Machine Learning Studio, vea la página Aprendizaje automático automatizado (en Creación).

![alt text](image.png)

Cree un nuevo trabajo de ML automatizado con la siguiente configuración, utilizando Next según sea necesario para progresar por la interfaz de usuario:
![alt text](image-2.png)

Ajustes básicos:

Nombre del trabajo: mslearn-bike-automl
Nuevo nombre del experimento: mslearn-bike-rental
Descripción: Aprendizaje automático automatizado para la predicción del alquiler de bicicletas
Etiquetas: ninguna

![alt text](image-3.png)

Tipo de tarea y datos:

Seleccione el tipo de tarea: Regresión
Seleccionar conjunto de datos: cree un nuevo conjunto de datos con la siguiente configuración:
Tipo de datos:
Nombre: alquiler de bicicletas
Descripción: Datos históricos de alquiler de bicicletas
Tipo: Tabular
Fuente de datos:
Seleccionar De archivos web
URL web:
URL web: https://aka.ms/bike-rentals
Omitir validación de datos: no seleccione
Ajustes:
Formato de archivo: Delimitado
Delimitador: Coma
Codificación: UTF-8
Encabezados de columna: solo el primer archivo tiene encabezados
Saltar filas: Ninguna
El conjunto de datos contiene datos de varias líneas: no seleccione
Esquema:
Incluir todas las columnas que no sean Ruta de acceso
Revisión de los tipos detectados automáticamente
Seleccione Crear. Una vez creado el conjunto de datos, seleccione el conjunto de datos de alquiler de bicicletas para seguir enviando el trabajo de ML automatizado.

![alt text](image-4.png)


Tipo de tarea y datos:

Seleccione el tipo de tarea: Regresión
Seleccionar conjunto de datos: cree un nuevo conjunto de datos con la siguiente configuración:
Tipo de datos:
Nombre: alquiler de bicicletas
Descripción: Datos históricos de alquiler de bicicletas
Tipo: Tabular
![alt text](image-5.png)


Fuente de datos:
Seleccionar De archivos web

![alt text](image-6.png)

URL web:
URL web: https://aka.ms/bike-rentals
Omitir validación de datos: no seleccione

![alt text](image-7.png)


Ajustes:
Formato de archivo: Delimitado
Delimitador: Coma
Codificación: UTF-8
Encabezados de columna: solo el primer archivo tiene encabezados
Saltar filas: Ninguna
El conjunto de datos contiene datos de varias líneas: no seleccione

![alt text](image-8.png)

Esquema:
Incluir todas las columnas que no sean Ruta de acceso
Revisión de los tipos detectados automáticamente
![alt text](image-9.png)


Seleccione Crear. Una vez creado el conjunto de datos, seleccione el conjunto de datos de alquiler de bicicletas para seguir enviando el trabajo de ML automatizado.
![alt text](image-10.png)


Configuración de tareas:

Tipo de tarea: Regresión
Conjunto de datos: alquiler de bicicletas
Columna de destino: Alquileres (entero)
Ajustes de configuración adicionales
![alt text](image-11.png)

Métrica principal: Error cuadrático medio normalizado
Explique el mejor modelo: No seleccionado
Usar todos los modelos compatibles: Unseleccionado. Restringirá el trabajo para probar solo unos pocos algoritmos específicos.
Modelos permitidos: seleccione solo RandomForest y LightGBM: normalmente querrá probar tantos como sea posible, pero cada modelo agregado aumenta el tiempo que se tarda en ejecutar el trabajo.
![alt text](image-12.png)


Límites: Expanda esta sección
Número máximo de pruebas: 3
Número máximo de ensayos simultáneos: 3
Número máximo de nodos: 3
Umbral de puntuación de métrica: 0,085 (de modo que si un modelo alcanza una puntuación de métrica de error cuadrático medio normalizado de 0,085 o menos, el trabajo finaliza.)
Tiempo de espera: 15
Tiempo de espera de iteración: 15
Habilitar terminación anticipada: Seleccionado

![alt text](image-13.png)

Validación y prueba:
Tipo de validación: división de validación de entrenamiento
Porcentaje de datos de validación: 10
Conjunto de datos de prueba: Ninguno
![alt text](image-14.png)


Cómputo:

Seleccione el tipo de proceso: Sin servidor
Tipo de máquina virtual: CPU
Nivel de máquina virtual: dedicado
Tamaño de la máquina virtual: Standard_DS3_V2*
Número de instancias: 1
* Si la suscripción restringe los tamaños de máquina virtual disponibles, elija el tamaño disponible.
![alt text](image-15.png)

Envíe el trabajo de capacitación. Se inicia automáticamente.

Espere a que finalice el trabajo. Puede tomar un tiempo, ¡ahora podría ser un buen momento para tomar un café!
![alt text](image-16.png)





Revisa el mejor modelo
Una vez finalizado el trabajo de aprendizaje automático automatizado, puede revisar el mejor modelo que ha entrenado.

En la pestaña Información general del trabajo de aprendizaje automático automatizado, anote el mejor resumen del modelo. Captura de pantalla del mejor resumen del modelo del trabajo de aprendizaje automático automatizado con un cuadro alrededor del nombre del algoritmo.

Nota Es posible que vea un mensaje en el estado "Advertencia: Se ha alcanzado la puntuación de salida especificada por el usuario...". Este es un mensaje esperado. Continúe con el siguiente paso.

Seleccione el texto en Nombre del algoritmo para ver el mejor modelo para ver sus detalles.

Seleccione la pestaña Métricas y seleccione los gráficos de valores residuales y predicted_true si aún no están seleccionados.

Revise los gráficos que muestran el rendimiento del modelo. El gráfico de residuos muestra los valores residuales (las diferencias entre los valores predichos y reales) como un histograma. El gráfico predicted_true compara los valores predichos con los valores reales.