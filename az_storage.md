# Laboratorio: Aprovisionamiento de una Cuenta de Almacenamiento en Azure

Este documento detalla el paso a paso del despliegue y aprovisionamiento de una cuenta de Azure Storage Account como contenedor principal para servicios de datos.

---

## Desarrollo del Laboratorio y Evidencias

### Paso 1: Inicio de sesión en el Portal de Azure
* Se accedió al portal oficial de administración de Microsoft Azure con las credenciales de la suscripción activa.
* **Evidencia:** ![Paso 1 - Inicio de sesión](URL_DE_LA_IMAGEN_1)

### Paso 2: Creación de un nuevo recurso
* En la página de inicio, se seleccionó la opción **＋ Create a resource** en la esquina superior izquierda.
* Se buscó el servicio **Storage account** en el Marketplace y se hizo clic en **Create**.
* **Evidencia:** ![Paso 2 - Búsqueda en Marketplace](URL_DE_LA_IMAGEN_2)

### Paso 3: Configuración de los detalles básicos (Basics)
* Se definieron los parámetros principales del ciclo de vida y costos del recurso:
  * **Suscripción:** Azure for Students.
  * **Grupo de recursos:** Creación de uno nuevo denominado `dp900-lab-rg`.
  * **Nombre de la cuenta:** `xtoragedp900` (nombre único en minúsculas y números).
  * **Región:** (Europe) Spain Central.
  * **Rendimiento:** Standard (nivel básico recomendado).
  * **Redundancia:** Locally-redundant storage (LRS) para optimizar costos de laboratorio.
* **Evidencia:** ![Paso 3 - Pestaña Basics](URL_DE_LA_IMAGEN_3)

### Paso 4: Revisión de Opciones Avanzadas (Advanced)
* Se navegó a la pestaña **Advanced** para examinar la configuración del espacio de nombres jerárquico (Hierarchical Namespace) necesario para Data Lake Storage Gen2.
* Siguiendo las instrucciones, se dejó la opción desmarcada para habilitarla en fases posteriores.
* **Evidencia:** ![Paso 4 - Pestaña Advanced](URL_DE_LA_IMAGEN_4)

### Paso 5: Configuración de la Protección de Datos (Data protection)
* Se accedió a la pestaña **Data protection**.
* En la sección de **Recovery**, se desmarcaron todas las casillas de **Enable soft delete...** para evitar conflictos de retención al cambiar al espacio de nombres jerárquico posteriormente.
* **Evidencia:** ![Paso 5 - Pestaña Data Protection](URL_DE_LA_IMAGEN_5)

### Paso 6: Validación y Revisión Final (Review + create)
* Se continuó por el asistente manteniendo los valores por defecto en redes y seguridad.
* En la pestaña **Review + create**, el sistema ejecutó la validación de configuraciones con éxito. Se procedió a hacer clic en **Create**.
* **Evidencia:** ![Paso 6 - Validación y Creación](URL_DE_LA_IMAGEN_6)

### Paso 7: Despliegue Exitoso y Acceso al Recurso
* El portal notificó la finalización del despliegue con el mensaje *"Your deployment is complete"*.
* Se confirmó la creación del recurso bajo el grupo `dp900-lab-rg` y se seleccionó **Go to resource** para su gestión.
* **Evidencia:** ![Paso 7 - Despliegue Completado](URL_DE_LA_IMAGEN_7)
