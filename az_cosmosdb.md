# Laboratorio: Crear una cuenta de Azure Cosmos DB

"Provisionar" simplemente significa crear y configurar un nuevo recurso en la nube. Para utilizar Cosmos DB, primero debes crear una cuenta de Azure Cosmos DB. En este laboratorio, configurarás una cuenta optimizada para almacenar y consultar datos estructurados en formato JSON utilizando la API nativa para NoSQL.

---

### Paso 1: Buscar el servicio en el Portal de Azure
* Haz clic en **+ Create a resource** (+ Crear un recurso) en la esquina superior izquierda del portal de Azure.
* En la barra de búsqueda del Marketplace, escribe `cosmo`.
* En los resultados sugeridos, selecciona **Azure Cosmos DB** y presiona **Create**.

> **Evidencia del paso 1:**
> ![Buscar Cosmos DB en el Marketplace](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/1cosmo.png)

---

### Paso 2: Seleccionar la API del motor de datos
* Localiza el panel correspondiente a **Azure Cosmos DB for NoSQL**.
* Haz clic en el botón **Create** situado en la parte inferior de dicha tarjeta.

* **Nota técnica:** Elegir la API para NoSQL te permite almacenar, indexar y consultar documentos JSON flexibles utilizando un lenguaje declarativo muy similar al SQL tradicional.

> **Evidencia del paso 2:**
> ![Selección de Azure Cosmos DB for NoSQL](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/2cosmo.png)

---

### Paso 3: Configurar los detalles de la instancia
Introduce los siguientes valores obligatorios en la pestaña de configuración básica:

* **Workload Type:** Learning (Ajusta los valores predeterminados para entornos de aprendizaje inicial y costos mínimos).
* **Subscription:** Selecciona tu suscripción activa (por ejemplo, *Azure for Students* o *Concierge Subscription* si estás en un sandbox).
* **Resource group:** Selecciona o crea un nuevo grupo de recursos único (en la práctica se utilizó `dp900-cosmos-rg`).
* **Account Name:** Ingresa un identificador único global (en la práctica se utilizó `minex`, habiéndose probado previamente `dp900-cosmos-2026`).
* **Availability Zones:** Disable.
* **Location:** Selecciona una región recomendada y cercana para minimizar la latencia de red (en la práctica se configuró `Spain Central` tras corregir un error inicial de validación regional en `Sweden Central`).
* **Capacity mode:** Provisioned throughput (Mantiene un rendimiento garantizado y predecible).
* **Apply Free-Tier Discount:** Selecciona **Apply** si se encuentra disponible para evitar cargos en el balance.
* **Limit total account throughput:** Mantén esta casilla sin seleccionar.

Una vez validados todos los campos requeridos, haz clic en el botón **Review + create** ubicado en la esquina inferior izquierda.

> **Evidencias del paso 3:**
> ![Configuración inicial de parámetros y modo de capacidad](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/3cosmo.png)
> ![Corrección regional y manejo de errores de validación](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/3.1cosmo.png)

---

### Paso 4: Validación final y creación del recurso
* El portal ejecutará un proceso de validación automatizado sobre tu arquitectura declarada.
* Una vez que aparezca el banner verde con la confirmación de **Validation Success**, revisa los términos del resumen técnico.
* Haz clic en el botón **Create** en la parte inferior izquierda de la pantalla.

> **Evidencia del paso 4:**
> ![Validación exitosa del esquema de Cosmos DB](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/4cosmo.png)

---
# Laboratorio: Crear una base de datos de ejemplo en Azure Cosmos DB

A lo largo de este procedimiento, puedes cerrar de forma segura cualquier ventana de sugerencias o "tips" que se muestren automáticamente en el portal.

---

### Paso 1: Acceder al Explorador de Datos (Data Explorer)
* En el panel de navegación izquierdo de tu nueva cuenta de Azure Cosmos DB, localiza y selecciona la opción **Data Explorer**.

> **Evidencia del paso 1:**
> ![Acceso al Data Explorer](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/1Cosm.png)

---

### Paso 2: Iniciar el Asistente de Inicio Rápido
* Dentro de la interfaz principal de Data Explorer, haz clic en el botón central llamado **Launch quick start** (Iniciar inicio rápido).

* **Nota técnica:** La función *Quick start* crea automáticamente una base de datos operativa, un contenedor y un conjunto de datos ficticios de ejemplo. Esto te permite practicar la inserción y consulta de elementos JSON de inmediato, sin la necesidad de diseñar un esquema estructural desde cero.

> **Evidencia del paso 2:**
> ![Iniciar Quick Start](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/2Cosm.png)

---

### Paso 3: Revisar y confirmar los parámetros del contenedor
* En el panel lateral derecho **New Container**, revisa las configuraciones preestablecidas de manera automática:
    * **Database id:** `SampleDB`
    * **Container id:** `SampleContainer`
    * **Partition key:** `/categoryId`
* Haz clic en **OK** para confirmar el aprovisionamiento. Si aparece un tutorial guiado flotante a un costado, puedes avanzar con *Next* o cerrarlo directamente presionando **OK** para continuar.

* **¿Qué es una clave de partición (Partition Key)?** Al estructurar un contenedor, Azure Cosmos DB requiere una propiedad específica de tus datos (como `categoryId`) para agrupar lógicamente los elementos relacionados. Cosmos DB distribuye estos grupos de manera interna a través del almacenamiento y cómputo subyacente para garantizar que la base de datos mantenga bajas latencias a gran escala. En proyectos reales, elegir una clave con alta cardinalidad (muchos valores distintos) y que sea frecuentemente utilizada en los filtros de tus consultas es una de las decisiones de diseño arquitectónico más críticas.

> **Evidencia del paso 3:**
> ![Aprovisionamiento automático de SampleDB y SampleContainer](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/3Cosm.png)

---

### Paso 4: Monitorear el estado de la creación e Implementación del recurso
* Observa la barra de estado y notificaciones en el panel inferior de la pantalla.
* Espera aproximadamente un minuto hasta que el sistema confirme que la base de datos `SampleDB` y su respectivo contenedor `SampleContainer` han sido creados e indexados correctamente.
* Espera unos minutos a que el portal de Azure complete el despliegue físico de la infraestructura en la región seleccionada.
* Una vez finalizado el proceso de aprovisionamiento, haz clic en el botón **Go to resource** (Ir al recurso) para acceder al panel de control de tu nueva cuenta de Azure Cosmos DB.
  
* > **Evidencia del paso 4:**
> ![Verificación de la creación exitosa del contenedor](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/4Cosm.png)

# Laboratorio: Visualizar y crear elementos en Azure Cosmos DB

---

### Paso 1: Explorar los elementos existentes (Items)
* En la interfaz de **Data Explorer**, despliega la base de datos `SampleDB` y expande el contenedor `SampleContainer`.
* Haz clic en la sección **Items** para listar los registros almacenados en el contenedor.
* Selecciona cualquiera de los elementos de la lista para visualizar su representación en formato estructurado JSON en el panel de lectura derecho. Cada elemento representa un producto con un `id` único y propiedades específicas.

> **Evidencia del paso 1:**
> ![Visualización de ítems y estructura JSON](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/comos1.png)

---

### Paso 2: Inicializar la creación de un nuevo elemento
* En la barra de herramientas superior de la página, haz clic en la opción **New Item** (Nuevo elemento) para abrir un documento JSON en blanco con una estructura base predeterminada.

> **Evidencia del paso 2:**
> ![Creación de un nuevo ítem en blanco](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/comos2.png)

---

### Paso 3: Modificar y guardar el documento JSON
* Reemplaza el bloque de texto en el editor con la información técnica del siguiente producto estructurado y presiona el botón **Save** (Guardar) de la barra superior:

json
{
    "name": "Road Helmet,45",
    "id": "123456789",
    "categoryId": "123456789",
    "SKU": "AB-1234-56",
    "description": "The product called \"Road Helmet,45\" ",
    "price": 48.74
}

> **Evidencia del paso 3:**
> ![Reemplazo de item JSON](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/comos3.png)

> ![Inclusión de Metadata automatica en el nuevo item JSON](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/comos3.1.png)

# Laboratorio: Realizar consultas en la base de datos de Azure Cosmos DB

---

### Paso 1: Abrir el editor de consultas SQL
* En la sección **Data Explorer** de la cuenta de Cosmos DB (`cosmos100`), despliega tu base de datos y contenedor.
* Selecciona el icono **New SQL Query** (Nueva consulta SQL) en la barra de herramientas superior para abrir una pestaña de ejecución de comandos.

> **Evidencia del paso 1:**
> ![Abrir pestaña de consultas SQL](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/1.png)

---

### Paso 2: Revisar la consulta por defecto
* Al inicializar la ventana, se posterior o automáticamente mostrará la consulta estructurada por defecto del motor NoSQL: `SELECT * FROM c`.
* El sistema queda listo en espera de la ejecución para mapear los documentos estructurados del contenedor.

> **Evidencia del paso 2:**
> ![Editor de consultas con comando por defecto](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/2.png)

---

### Paso 3: Ejecutar la consulta base y revisar los resultados
* Haz clic en el botón **Ejecutar la consulta** (Execute Query).
* En el panel inferior **Results**, analiza la respuesta del motor. El resultado devuelve un array con la representación JSON completa de todos los elementos almacenados dentro de `SampleContainer`.

> **Evidencia del paso 3:**
> ![Resultados de la consulta general NoSQL](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/3.png)

---

### Paso 4: Modificar la consulta para aplicar un filtro de texto
* Edita el código de la pestaña de ejecución SQL para buscar términos específicos dentro de los documentos utilizando la función condicional `CONTAINS`:

sql
SELECT *
FROM c
WHERE CONTAINS(c.name, "Helmet")

> **Evidencia del paso 4:**
> ![Resultados de la consulta general NoSQL](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/4.png)


### Paso 5: Ejecutar la consulta filtrada y validar respuestas
* Comprueba los documentos JSON resultantes en el panel inferior; ahora el sistema solo expone las entidades cuyo atributo de nombre contiene explícitamente la palabra "Helmet" (por ejemplo, el producto "Sport-100 Helmet, Black").

> **Evidencia del paso 5:**
> ![Ejecutar la consulta](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/5.png)


### Paso 6: Cerrar el editor de consultas
* Finaliza la sesión de pruebas cerrando la pestaña del editor SQL en el portal de Azure presionando la 'X' de la pestaña o el botón de descartar cambios.

> **Evidencia del paso 6:**
> ![Resultados de la consulta general NoSQL](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/6.png)

### Paso 7: Eliminación del recurso
> **Evidencia del paso 7:**
> ![Eliminacion del recurso](https://github.com/camilogrey/Lab2-Azure-Data-non-relational-Azure-Storage-CosmosDB/blob/main/7.png)
