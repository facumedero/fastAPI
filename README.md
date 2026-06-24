# FastAPI Todo API 🚀

Este es un proyecto backend sencillo desarrollado con **FastAPI** y **Pydantic** para gestionar una lista de tareas (Items). Permite crear ítems, listarlos y buscar un ítem específico por su ID.

## 🛠️ Tecnologías utilizadas

* **Python 3.14+**
* **FastAPI**: Framework web moderno y rápido.
* **Pydantic**: Validación de datos y gestión de configuraciones mediante tipos de Python.
* **Uvicorn**: Servidor ASGI rápido para producción y desarrollo.

---

## 🚀 Instalación y Configuración

Sigue estos pasos para clonar el repositorio y correr el proyecto localmente.

### 1. Clonar el repositorio

```bash
git clone https://github.com/facumedero/fastAPI.git
cd fastAPI
```

### 2. Crear y activar un entorno virtual (Recomendado)

En Windows (PowerShell):

```powershell
python -m venv venv
.\venv\Scripts\Activate.ps1
```

### 3. Instalar dependencias

```bash
pip install fastapi uvicorn pydantic
```

### 4. 🏃 Encender el servidor

Para levantar la API en modo de desarrollo (con recarga automática al guardar cambios), ejecuta:

```powershell
python -m uvicorn main:app --reload
```

El servidor se iniciará en: [http://127.0.0.1:8000](http://127.0.0.1:8000)

---

## 📌 Endpoints Disponibles

### 🏠 Base

* **GET `/`**: Retorna un mensaje de bienvenida en formato JSON.

### 📦 Gestión de Items

* **POST `/items`**: Crea un nuevo ítem.
  
  * **Body (JSON):**
  
    ```json
    {
      "text": "Comprar manzanas",
      "is_done": false
    }
    ```

* **GET `/items`**: Lista todos los ítems guardados en memoria.
  * **Query Parameters:** `limit` (Opcional, por defecto 10).

* **GET `/items/{item_id}`**: Obtiene un ítem por su índice/ID numérico. Devuelve un error `404` si no existe.

---

## 🧪 ¿Cómo probar la API?

### 1. Documentación Interactiva (Swagger UI) 🌟

FastAPI genera documentación automática de forma nativa. Una vez encendido el servidor, puedes ingresar a:

* **Swagger UI:** [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs) (Para probar los endpoints desde el navegador).
* **ReDoc:** [http://127.0.0.1:8000/redoc](http://127.0.0.1:8000/redoc)

### 2. Probando desde la consola (cURL)

Recuerda usar `curl.exe` si estás en PowerShell en Windows:

* **Probar GET básico:**
  
  ```powershell
  curl.exe http://127.0.0.1:8000/
  ```

* **Probar crear un ítem (POST):**
  
  ```powershell
  curl.exe -X POST -H "Content-Type: application/json" -d '{"text": "Aprender FastAPI", "is_done": false}' http://127.0.0.1:8000/items
  ```

* **Probar obtener el ítem creado (GET por ID):**
  
  ```powershell
  curl.exe http://127.0.0.1:8000/items/0
  ```
