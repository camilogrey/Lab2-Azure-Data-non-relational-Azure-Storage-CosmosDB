# Laboratorio: Aprovisionamiento de una Cuenta de Almacenamiento en Azure

Este documento detalla el paso a paso del despliegue y aprovisionamiento de una cuenta de Azure Storage Account como contenedor principal para servicios de datos.

---

## Desarrollo del Laboratorio y Evidencias

### Paso 1: Inicio de sesión en el Portal de Azure
* Se accedió al portal oficial de administración de Microsoft Azure con las credenciales de la suscripción activa.
* **Evidencia:** ![Paso 1 - Inicio de sesión](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/3eb7014f919053edc1e9a6d0b1f5d269569de579/AZStorage1.png)

### Paso 2: Creación de un nuevo recurso
* En la página de inicio, se seleccionó la opción **＋ Create a resource** en la esquina superior izquierda.
* Se buscó el servicio **Storage account** en el Marketplace y se hizo clic en **Create**.
* **Evidencia:** ![Paso 2 - Búsqueda en Marketplace](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/3eb7014f919053edc1e9a6d0b1f5d269569de579/AZStorage2.png))

### Paso 3: Configuración de los detalles básicos (Basics)
* Se definieron los parámetros principales del ciclo de vida y costos del recurso:
  * **Suscripción:** Azure for Students.
  * **Grupo de recursos:** Creación de uno nuevo denominado `dp900-lab-rg`.
  * **Nombre de la cuenta:** `xtoragedp900` (nombre único en minúsculas y números).
  * **Región:** (Europe) Spain Central.
  * **Rendimiento:** Standard (nivel básico recomendado).
  * **Redundancia:** Locally-redundant storage (LRS) para optimizar costos de laboratorio.
* **Evidencia:** ![Paso 3 - Pestaña Basics](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/3eb7014f919053edc1e9a6d0b1f5d269569de579/AZStorage3.png)

### Paso 4: Revisión de Opciones Avanzadas (Advanced)
* Se navegó a la pestaña **Advanced** para examinar la configuración del espacio de nombres jerárquico (Hierarchical Namespace) necesario para Data Lake Storage Gen2.
* Siguiendo las instrucciones, se dejó la opción desmarcada para habilitarla en fases posteriores.
* **Evidencia:** ![Paso 4 - Pestaña Advanced](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/3eb7014f919053edc1e9a6d0b1f5d269569de579/AZStorage4.png)

### Paso 5: Configuración de la Protección de Datos (Data protection)
* Se accedió a la pestaña **Data protection**.
* En la sección de **Recovery**, se desmarcaron todas las casillas de **Enable soft delete...** para evitar conflictos de retención al cambiar al espacio de nombres jerárquico posteriormente.
* **Evidencia:** ![Paso 5 - Pestaña Data Protection](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/3eb7014f919053edc1e9a6d0b1f5d269569de579/AZStorage5.png)

### Paso 6: Validación y Revisión Final (Review + create)
* Se continuó por el asistente manteniendo los valores por defecto en redes y seguridad.
* En la pestaña **Review + create**, el sistema ejecutó la validación de configuraciones con éxito. Se procedió a hacer clic en **Create**.
* **Evidencia:** ![Paso 6 - Validación y Creación](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/3eb7014f919053edc1e9a6d0b1f5d269569de579/AZStorage6.png)

### Paso 7: Despliegue Exitoso y Acceso al Recurso
* El portal notificó la finalización del despliegue con el mensaje *"Your deployment is complete"*.
* Se confirmó la creación del recurso bajo el grupo `dp900-lab-rg` y se seleccionó **Go to resource** para su gestión.
* **Evidencia:** ![Paso 7 - Despliegue Completado](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/3eb7014f919053edc1e9a6d0b1f5d269569de579/AZStorage7.png)

# Laboratorio: Explore Blob Storage

Desarrollo y evidencias del ejercicio práctico para la creación de contenedores de blobs y el análisis del comportamiento de un espacio de nombres plano (*flat namespace*).

---

## Desarrollo del Laboratorio y Evidencias

### Paso 1: Descargar archivo JSON
* Se descargó el archivo de datos `product1.json` en el equipo local.
* **Evidencia:** ![Paso 1](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/fb47b527690158183a43adc2cc00430c5ee26c5d/azblob1.png)

### Paso 2: Navegar a la sección Containers
* Dentro del menú lateral izquierdo de la cuenta de almacenamiento, en la sección **Data storage**, se seleccionó **Containers**.
* **Evidencia:** ![Paso 2](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/fb47b527690158183a43adc2cc00430c5ee26c5d/azblob2.png)

### Paso 3: Configurar el nuevo contenedor
* Se seleccionó **＋ Add container** y se asignó el nombre `data`. El nivel de acceso anónimo se estableció automáticamente como *Private*.
* **Evidencia:** ![Paso 3](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/azblob3.png)

### Paso 4: Verificar creación del contenedor
* Se confirmó que el contenedor creado aparece listado de manera correcta en el panel principal.
* **Evidencia:** ![Paso 4](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/azblob4.png)

### Paso 5: Abrir Storage browser
* En la parte superior del panel izquierdo se seleccionó la herramienta **Storage browser** para interactuar con los datos.
* **Evidencia:** ![Paso 5](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/azblob5.png)

### Paso 6: Listar contenedores de blobs
* Dentro del explorador de almacenamiento, se hizo clic en **Blob containers** para ver los recursos.
* **Evidencia:** ![Paso 6](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/azblob6.png)

### Paso 7: Comprobar contenedor vacío
* Se seleccionó el contenedor `data` y se observó que no contenía elementos inicialmente.
* **Evidencia:** ![Paso 7](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/azblob7.png)

### Paso 8: Agregar directorio virtual
* Se hizo clic en la opción **＋ Add Directory** para configurar una nueva carpeta llamada `products`.
* **Evidencia:** ![Paso 8](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/azblob8.png)

### Paso 9: Comprobar la ruta en el explorador
* Se validó que la sección superior (*breadcrumbs*) mostrara correctamente la ruta estructurada `Blob containers > data > products`.
* **Evidencia:** ![Paso 9](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/azblob9.png)

### Paso 10: Comprobación del espacio de nombres plano (*Flat Namespace*)
* Al hacer clic de vuelta sobre `data`, se comprobó que el directorio `products` no existía realmente por no contener ningún blob dentro de él.
* **Evidencia:** ![Paso 10](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/azblob10.png)

### Paso 11: Abrir panel de carga
* Se hizo clic en el botón **⤒ Upload** para desplegar el asistente de subida de archivos.
* **Evidencia:** ![Paso 11]([Sin imagen](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/azblob11.png))*

### Paso 12: Cargar archivo indicando ruta de carpeta
* Se seleccionó el archivo local `product1.json`. En la sección avanzada, dentro de **Upload to folder**, se escribió `product_data` antes de ejecutar la carga.
* **Evidencia:** ![Paso 12](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/azblob12.png)

### Paso 13: Verificar creación automática de la carpeta virtual
* Tras cerrar el panel, se validó la presencia de la nueva ruta virtual `product_data` generada por la existencia del blob.
* **Evidencia:** ![Paso 13](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/azblob13.png)*

### Paso 14: Confirmar el blob almacenado
* Al abrir la ruta `product_data`, se comprobó que el archivo `product1.json` se encontraba almacenado de manera correcta.
* **Evidencia:** ![Paso 14](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/azblob14.png)

### Paso 15: Regresar a la sección general de Containers
* Desde el panel de navegación izquierdo se volvió a ingresar al menú principal de **Containers**.
* **Evidencia:** ![Paso 15](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/azblob15.png)

### Paso 16: Inspeccionar el contenedor de datos
* Se abrió nuevamente el contenedor `data` para listar el contenido desde la vista general.
* **Evidencia:** ![Paso 16](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/azblob16.png)

### Paso 17: Validar limitaciones de administración de carpetas virtuales
* Se seleccionó el ícono de los tres puntos (**...**) al final de la carpeta y se constató que no existen opciones de gestión, demostrando que no es un directorio real sino un prefijo de nombre.
* **Evidencia:** ![Paso 17](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/azblob17.png)

### Paso 18: Retornar al panel principal
* Se utilizó el ícono **X** en la parte superior derecha para cerrar la vista del contenedor y volver al listado general.
**Evidencia:** ![Paso 18](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/azblob18.png)

# Laboratorio: Explore Azure Data Lake Storage Gen2

Desarrollo y evidencias del proceso de actualización de la cuenta de almacenamiento para habilitar el espacio de nombres jerárquico (*hierarchical namespace*).

---

## Desarrollo del Laboratorio y Evidencias

### Paso 1: Descargar el segundo archivo JSON
* Se descargó el archivo complementario `product2.json` en el equipo local.
* **Evidencia:** ![Paso 1](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/1gen.png)

### Paso 2: Acceder a la opción de actualización
* En el menú lateral izquierdo de la cuenta de almacenamiento, bajo la sección **Settings**, se seleccionó **Data Lake Gen2 upgrade**.
* **Evidencia:** ![Paso 2](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/2gen.png)

### Paso 3: Ejecutar la actualización a Gen2
* Se completaron los pasos de validación del asistente y se aplicó la actualización irreversible de la cuenta hacia capacidades de Data Lake Gen2.
* **Evidencia:** ![Paso 3](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/3gen.png)

### Paso 4: Validar persistencia en Storage browser
* Tras la actualización, se navegó a **Storage browser** en la raíz del contenedor `data` para confirmar que el directorio `product_data` persistió correctamente.
* **Evidencia:** ![Paso 4](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/4gen.png)

### Paso 5: Confirmar integridad del blob previo
* Se ingresó a la carpeta `product_data` y se comprobó que el archivo `product1.json` seguía disponible sin alteraciones.
* **Evidencia:** ![Paso 5](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/5gen.png)

### Paso 6: Abrir panel de carga
* Se hizo clic en el botón **⤒ Upload** para abrir la pestaña lateral de carga de objetos.
* **Evidencia:** ![Paso 6](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/6gen.png)

### Paso 7: Seleccionar el nuevo archivo de datos
* Se adjuntó el archivo local `product2.json` en el asistente de subida para añadirlo a la ruta actual.
* **Evidencia:** ![Paso 7](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/7gen.png)

### Paso 8: Confirmar coexistencia de archivos
* Tras finalizar la carga, se validó que ambos archivos (`product1.json` y `product2.json`) coexisten dentro del mismo directorio.
* **Evidencia:** ![Paso 8](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/8gen.png)

### Paso 9: Regresar al menú Containers
* En la sección **Data storage** del panel de control izquierdo, se seleccionó nuevamente la opción general de **Containers**.
* **Evidencia:** ![Paso 9](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/9gen.png)

### Paso 10: Inspeccionar la vista del contenedor jerárquico
* Se abrió el contenedor `data` para visualizar la estructura real de directorios ahora soportada por la cuenta de almacenamiento.
* **Evidencia:** ![Paso 10](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/10gen.png)

### Paso 11: Verificar opciones avanzadas de carpeta (Sin Imagen)
* Se interactuó con el menú de tres puntos (**...**) a la derecha del directorio. Al habilitar el espacio de nombres jerárquico, se verificó la disponibilidad de herramientas reales de gestión como renombrar rutas y configurar permisos a nivel de carpeta (**Manage ACL**).
* **Evidencia:** ![Paso 11](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/11gen.png)
### Paso 12: Cerrar la interfaz del contenedor (Sin Imagen)
* Se utilizó el ícono **X** en la esquina superior derecha para concluir el ejercicio y retornar al listado de contenedores.
* **Evidencia:** ![Paso 12](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/12gen.png)

# Laboratorio: Explore Azure Files

Desarrollo y evidencias del proceso de creación de recursos de almacenamiento compartido basados en la nube y análisis de los métodos de conectividad multiplataforma.

---

## Desarrollo del Laboratorio y Evidencias

### Paso 1: Navegar a la sección Classic file shares
* En el panel de control izquierdo, bajo la sección **Data storage**, se seleccionó la opción **Classic file shares**.
* Se constató que, debido a la habilitación previa del espacio de nombres jerárquico (Gen2), la administración se realiza bajo la categoría clásica.
* **Evidencia:** ![Paso 1](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/1files.png)

### Paso 2: Configurar los detalles básicos del recurso compartido
* Se seleccionó el botón **＋ Classic file share**.
* En la pestaña **Basics**, se asignó el nombre `files` y se mantuvo el nivel de acceso en la opción por defecto **Transaction optimized**.
* **Evidencia:** ![Paso 2](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/2files.png)

### Paso 3: Deshabilitar políticas de respaldo y confirmación
* En la pestaña **Backup**, se desmarcó la opción **Enable backup** para optimizar el consumo del laboratorio.
* Posteriormente, se procedió a la validación final y creación del recurso compartido.
* **Evidencia:** ![Paso 3](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/3files.png)

### Paso 4: Abrir el recurso compartido creado
* Una vez completado el despliegue, se ingresó al panel de administración general del recurso compartido denominado `files`.
* **Evidencia:** ![Paso 4](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/4files.png)

### Paso 5: Revisar scripts de conectividad híbrida
* Se seleccionó la opción **Connect** en la barra superior.
* El panel lateral expuso las pestañas dedicadas para Windows, Linux y macOS, mostrando los scripts nativos necesarios para montar la unidad de red mediante el protocolo SMB.
* **Evidencia:** ![Paso 5](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/5files.png)

### Paso 6: Verificación en el listado principal
* Se cerró el panel de conexión retornando a la vista general de la cuenta, verificando el estado activo y la cuota asignada del recurso compartido.
* **Evidencia:** ![Paso 6](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/6files.png)

### Paso 7: Clean up
* Eliminacion del recurso.
* **Evidencia:** ![Paso 7](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/Captura%20de%20pantalla%202026-06-25%20204303.png)
