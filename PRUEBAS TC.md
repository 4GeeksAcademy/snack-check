## Casos de prueba

Durante el desarrollo realicé varias pruebas para comprobar que el flujo funcionaba correctamente.

### Pruebas funcionales

TC-001 - Nutella (3017620422003)

- Resultado esperado: no saludable.
- Resultado obtenido: no saludable.


TC-002 - Coca-Cola (5449000000996)

- Resultado esperado: no saludable por Nutri-Score E.
- Resultado obtenido: no saludable.


TC-003 - Producto con Nutri-Score A

- Resultado esperado: saludable.


TC-004 - Producto con Nutri-Score C

- Resultado esperado: moderado.


 TC-005 - Producto sin datos nutricionales

- Resultado esperado: datos insuficientes.
- Resultado obtenido: datos insuficientes.

 TC-006 - Consulta a Open Food Facts

- Se recuperaron correctamente los datos nutricionales del producto.

 TC-007 - Generación de respuesta con Groq

- El sistema generó un veredicto en español acorde al resultado obtenido.

 TC-008 - Prueba completa mediante curl

- Resultado esperado: respuesta 200 en formato texto.

