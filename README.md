# Microsoft_Student_Technical_Training_MLSA-JEVG

## Machine learning basics
https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/01-machine-learning.html

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

