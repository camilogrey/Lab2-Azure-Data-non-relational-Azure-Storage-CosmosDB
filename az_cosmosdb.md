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

### Paso 5: Implementación del recurso
* Espera unos minutos a que el portal de Azure complete el despliegue físico de la infraestructura en la región seleccionada.
* Una vez finalizado el proceso de aprovisionamiento, haz clic en el botón **Go to resource** (Ir al recurso) para acceder al panel de control de tu nueva cuenta de Azure Cosmos DB.
