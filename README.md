# TPI-Desarrollo-de-Software-con-IA
Prototipo funcional de venta cruzada con IA y resiliencia en SQLite3
# Asistente Inteligente de Venta Cruzada (E-Commerce Crochet) 🧶🤖

Prototipo funcional desarrollado para la materia **Desarrollo de Software con IA (Ciclo Lectivo 2026)**.

## 📌 Historias de Usuario Implementadas (4 Funcionalidades)
1. **HU-01 (Gestión de Stock):** Consulta e ingesta del catálogo de insumos físicos (hilados y agujas) en SQLite.
2. **HU-04 (Filtrado de Patrones):** Búsqueda y filtrado dinámico de patrones digitales según nivel de dificultad.
3. **HU-03 [IA] (Asistente de Venta Cruzada con Fallback):** Integración en vivo con la API REST de Gemini para la recomendación de materiales con control de timeout (4s) y resiliencia (`ejecutarFallback()`).
4. **HU-02 (Registro de Compras):** Persistencia transaccional de órdenes de compra e interacciones en la base relacional.

## 🛠️ Tecnologías Utilizadas
- **Python 3** (Lenguaje principal y lógica asíncrona)
- **SQLite3** (Motor de base de datos relacional)
- **API REST Google Gemini** (Asistente generativo)

## 📁 Estructura del Repositorio
- `Tienda_crochet.ipynb`: Cuaderno/script principal con la ingesta relacional y el menú interactivo.
- `tienda_crochet.db`: Base de datos SQLite física con el esquema relacional y datos de prueba.
- `README.md`: Documentación del proyecto.

## 🚀 Instrucciones de Ejecución
1. Abrir el archivo `Tienda_crochet.ipynb` en Google Colab o un entorno Python local.
2. (Opcional) Configurar la clave de API de Gemini en la pestaña de Secretos de Colab con el nombre `GEMINI_API_KEY`.
3. Ejecutar las celdas en orden secuencial para inicializar el menú interactivo en consola.

## 🤖 Registro de Asistencia de IA en la Codificación
Durante el desarrollo se utilizó asistencia de IA Generativa para:
- Estructuración de las tablas relacionales (`PATRONES`, `HILADOS`, `AGUJAS`, `RECETA_INSUMOS`) y claves foráneas en SQLite.
- Definición de la llamada HTTP asíncrona mediante `asyncio.to_thread` con límite estricto de timeout a 4000 ms.
- Diseño del mecanismo de resiliencia ante errores/desconexión (`ejecutarFallback()`).
