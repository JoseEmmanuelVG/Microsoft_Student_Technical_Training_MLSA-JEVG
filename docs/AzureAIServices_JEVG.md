Exploración de los servicios de inteligencia artificial de Azure

Los servicios de inteligencia artificial de Azure ayudan a los usuarios a crear aplicaciones de inteligencia artificial con API y modelos listos para usar, precompilados y personalizables. En este ejercicio, echará un vistazo a uno de los servicios, Azure AI Content Safety, en Content Safety Studio.

Content Safety Studio le permite explorar cómo se puede moderar el contenido de texto e imagen. Puede ejecutar pruebas en texto o imágenes de muestra y obtener una puntuación de gravedad que va de segura a alta para cada categoría. En este ejercicio de laboratorio, creará un recurso de servicio único en Content Safety Studio y probará sus funcionalidades.


Nota El objetivo de este ejercicio es obtener una idea general de cómo se aprovisionan y usan los servicios de Azure AI. La seguridad del contenido se utiliza como ejemplo, pero no se espera que obtenga un conocimiento completo de la seguridad del contenido en este ejercicio.


Asociar un recurso con el estudio
Antes de usar el estudio, debe asociar un recurso de servicios de Azure AI con el estudio. Dependiendo del estudio, es posible que necesite un recurso de servicio único específico o que pueda usar un recurso general de varios servicios. En el caso de Content Safety Studio, puede usar el servicio mediante la creación de un recurso de seguridad de contenido de un solo servicio o un recurso multiservicio general de Azure AI Services. En los pasos que se indican a continuación, crearemos un recurso de seguridad de contenido de un solo servicio.

![alt text](image-17.png)



En la parte superior derecha de la pantalla, haga clic en el icono Configuración.
![alt text](image-18.png)


En la página Crear seguridad de contenido en Azure Portal, debe configurar varios detalles para crear el recurso. Configúrelo con los siguientes ajustes:
Suscripción: su suscripción de Azure.
Grupo de recursos: seleccione o cree un grupo de recursos con un nombre único.
Región: elija cualquier región disponible.
Nombre: escriba un nombre único.
Plan de tarifa: Free F0

![alt text](image-19.png)

Seleccione Revisar + Crear y revise la configuración. A continuación, seleccione Crear. La pantalla indicará cuándo se ha completado la implementación.
¡Felicidades! Acaba de crear o aprovisionar un recurso de servicios de Azure AI. El que ha aprovisionado en concreto es un recurso de servicio de seguridad de contenido de un solo servicio.

![alt text](image-20.png)

Cuando se complete la implementación, abra una nueva pestaña y vuelva a Content Safety Studio.

![alt text](image-21.png)

Vuelva a seleccionar el icono de Configuración en la parte superior derecha de la pantalla. Esta vez, debería ver que el recurso recién creado se ha agregado a la lista.

En la página Configuración de Content Safety Studio, seleccione el recurso de servicio Azure AI que acaba de crear y haga clic en Usar recurso en la parte inferior de la pantalla. Volverás a la página de inicio del estudio. Ahora puede comenzar a usar el estudio con el recurso recién creado.

![alt text](image-22.png)


Pruebe la moderación de texto en Content Safety Studio

En la página principal de Content Safety Studio, en Ejecutar pruebas de moderación, vaya al cuadro Moderar contenido de texto y haga clic en Pruébelo.
![alt text](image-24.png)

En Ejecutar una prueba simple, haga clic en Contenido seguro. Observe que el texto se muestra en el cuadro de abajo.
![alt text](image-23.png)

Haga clic en Ejecutar prueba. Al ejecutar una prueba, se llama al modelo de aprendizaje profundo del servicio de seguridad de contenido. El modelo de aprendizaje profundo ya ha sido entrenado para reconocer contenido no seguro.
![alt text](image-25.png)


En el panel Resultados, inspeccione los resultados. Hay cuatro niveles de gravedad, desde seguro hasta alto, y cuatro tipos de contenido dañino. ¿El servicio de IA de seguridad de contenido considera que esta muestra es aceptable o no? Lo que es importante tener en cuenta es que los resultados están dentro de un intervalo de confianza. Un modelo bien entrenado, como uno de los modelos listos para usar de Azure AI, puede devolver resultados que tienen una alta probabilidad de coincidir con lo que un humano etiquetaría como resultado. Cada vez que se ejecuta una prueba, se vuelve a llamar al modelo.
![alt text](image-26.png)




Ahora pruebe con otra muestra. Seleccione el texto en Contenido violento con faltas de ortografía. Compruebe que el contenido se muestra en el cuadro siguiente.
![alt text](image-27.png)

Haga clic en Ejecutar prueba e inspeccione de nuevo los resultados en el panel Resultados.
![alt text](image-28.png)

Puede ejecutar pruebas en todas las muestras proporcionadas y, a continuación, inspeccionar los resultados.




Echa un vistazo a las claves y al punto de conexión
Estas capacidades que probó se pueden programar en todo tipo de aplicaciones. Las claves y el punto de conexión que se usan para el desarrollo de aplicaciones se pueden encontrar tanto en Content Safety Studio como en Azure Portal.

En Content Safety Studio, vuelva a la página Configuración, con la pestaña Recursos seleccionada. Busca el recurso que utilizaste. Desplácese por aquí para ver el punto de conexión y la clave del recurso.
![alt text](image-29.png)

En el Portal de Azure, verá que se trata del mismo punto de conexión y claves diferentes para el recurso. Para comprobarlo, diríjase al Portal de Azure. Busque Seguridad de contenido en la barra de búsqueda superior. Busque su recurso y haga clic en él. En el menú de la izquierda, busque en Administración de recursos para claves y puntos de conexión. Seleccione Claves y puntos de conexión para ver el punto de conexión y las claves del recurso.
![alt text](image-30.png)



NOTA: Una vez que haya terminado, puede eliminar el recurso de seguridad de contenido del Portal de Azure. La eliminación del recurso es una manera de reducir los costos que se acumulan cuando el recurso existe en la suscripción. Para ello, vaya a la página Información general del recurso de seguridad del contenido. Seleccione Eliminar en la parte superior de la pantalla.

