# Changelog


### Descripción

Primera versión funcional de SnackCheck.

El proyecto recibe un código de barras, consulta la información del producto en Open Food Facts y devuelve un veredicto nutricional generado con ayuda de IA.

### Funcionalidades añadidas

- Creación del webhook `nutrition-check`.
- Recepción de códigos de barras mediante una petición POST.
- Validación de que el código existe.
- Validación de que el código contiene únicamente números.
- Consulta de productos usando la API de Open Food Facts.
- Obtención de datos nutricionales del producto.
- Clasificación de azúcar, sal y grasa.
- Cálculo del resultado mediante semáforo nutricional.
- Uso del Nutri-Score cuando está disponible.
- Generación de un veredicto final (saludable, moderado o no saludable).
- Cálculo de una puntuación de preocupación según los nutrientes altos encontrados.
- Generación de un mensaje explicativo usando IA (Groq).
- Respuesta final en formato texto para el usuario.

### Manejo de errores

Se añadieron respuestas específicas para:

- Código de barras no enviado.
- Código de barras no válido.
- Producto no encontrado.
- Datos nutricionales insuficientes.

### Estado del proyecto

 Workflow publicado.

 Integración con Open Food Facts funcionando.

 Integración con Groq funcionando.

 Flujo completo operativo en n8n.

Actualmente el workflow cuenta con 19 nodos.