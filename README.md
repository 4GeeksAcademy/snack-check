# snack-check

proyecto realizado en n8n que permite comprobar si un producto es saludable a partir del código de barras.

## ¿Que hace?

El usuario envia el código de barras mediante una petición.

el flujo busca el producto en Opeen Food Facts, obtiene la información nutricional y genera un veredicto en español:

-Saludable (verde)
-Moderado  (amarillo)
-No saludable (rojo)

## Cómo funciona

1. Recibe el código de barras.
2. Comprueba que el código sea válido.
3. Busca el producto en Open Food Facts.
4. Obtiene los datos nutricionales.
5. Analiza azúcar, sal y grasa.
6. Calcula un resultado usando el semáforo nutricional y el Nutri-Score.
7. Devuelve un mensaje fácil de entender para el usuario.

## flujo del proyecto

Recibe código, valida el código, busca el producto, obtiene datos nutricionales,clasifica datos nutricionales, genera veredicto y responde al usuario

## Uso

### Endpoint

```text
POST https://aitor510.app.n8n.cloud/webhook/nutrition-check
```

### Body

```json
{
  "barcode": "3017620422003"
}
```

## Reglas utilizadas

### Azúcar (por 100 g)

- Bajo: menos de 5 g
- Medio: entre 5 g y 22,5 g
- Alto: más de 22,5 g

### Sal

- Alto: más de 1,5 g

### Grasa

- Alto: más de 17,5 g

### Resultado del semáforo

- 0 valores altos → Saludable
- 1 valor alto → Moderado
- 2 o más valores altos → No saludable

### Nutri-Score

- A o B → Saludable
- C → Moderado
- D o E → No saludable

El resultado final siempre utiliza la clasificación más desfavorable.

## Respuestas

| Situación | Código |
|------------|---------|
| Veredicto generado | 200 |
| Datos insuficientes | 400 |
| Petición incorrecta | 400 |
| Producto no encontrado | 404 |

## APIs utilizadas

- Open Food Facts
- Groq

## limitaciones

este proyecto siempre respondera dependiendo la información disponible en Open Food Facts.