# n8n TFG - Arquitecturas de Chatbot

Este repositorio contiene los flujos de n8n correspondientes a las **3 arquitecturas** analizadas en el informe. Los archivos se encuentran en formato `.json` dentro de la carpeta `backups/` y pueden ser importados directamente a cualquier instancia de n8n.

## Cómo empezar

### 1. Descargar e instalar n8n
Existen dos formas rápidas de ejecutar n8n localmente (requiere Node.js). Abre una consola de comandos (**CMD**, **PowerShell** o **Terminal**) y ejecuta:

**Opción A: Instalación global (recomendada)**
```bash
npm install n8n -g
n8n
```

**Opción B: Ejecución directa (la más rápida)**
```bash
npx n8n
```

### 2. Importar los Workflows
Una vez que n8n esté corriendo (por defecto en `http://localhost:5678`):
1. Crea un nuevo workflow.
2. Arrastra el archivo `.json` deseado directamente al lienzo de n8n, o utiliza la opción **"Import from File"** en el menú del workflow.

## Requisitos de Configuración

Para que los nodos funcionen correctamente, es necesario configurar las credenciales de los siguientes servicios:
*   **Google Cloud:** Necesario para servicios de Google (Drive, Sheet para los Benchmarks, Modelos de IA, etc.). La versión gratuita es suficiente.
*   **Google Drive:** Para el almacenamiento de documentos y poder cargar el Manual de BMW.
*   **OpenAI:** Necesario para el procesamiento de lenguaje y embeddings.

### Notas Importantes
*   **Embeddings de OpenAI:** Los flujos utilizan el modelo `embedding-3-large`. Este modelo **no funciona con la versión de prueba gratuita** de OpenAI; requiere una cuenta con un depósito mínimo realizado.
*   **Alternativa Económica:** En el caso del flujo `Master Router - Sistema Multi-Arquitectura_ChatMotor`, si no deseas usar OpenAI para embeddings, puedes sustituir ese nodo por el de **Google Embedding**. Dado que en este flujo solo se realizan esfuerzos mínimos de búsqueda, los embeddings de Google funcionarán perfectamente y se pueden ejecutar bajo la capa gratuita de Google Cloud.
