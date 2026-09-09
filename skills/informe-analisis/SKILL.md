---
name: informe-analisis
description: >
  Usar cuando el usuario pasa el análisis de un activo (acción, cripto, índice, FX) en texto
  plano —o en notas sueltas, o dictado— y quiere el entregable listo para mandarle a un cliente:
  "pasame esto a informe", "armame el entregable de BKNG", "esto es lo que le quiero mandar a X".
  Convierte texto crudo en un Google Doc con formato, estructura de 8 secciones y auditoría de
  los datos que faltan. NO usar para el análisis en sí — la lectura del gráfico la hace el
  usuario, no esta skill — ni para gestionar un portafolio propio.
---

# Informe de análisis de activo

Convierte el texto plano del usuario en un entregable de cliente. **La lectura técnica es de él;
esta skill no analiza mercado ni opina sobre el activo** — estructura, traduce al castellano del
cliente, y marca lo que falta.

## La plantilla

`assets/plantilla.html`, dentro de esta misma skill, es la fuente de verdad del formato. Se copia
y se rellena, no se rediseña en cada informe. La skill es autocontenida: no depende de rutas de
ningún repo, así que funciona igual instalada global o dentro de un proyecto.

Estructura fija de 8 secciones:

1. Conclusión (sesgo, cómo se ejecuta, invalidación) · 2. Contexto · 3. Niveles clave ·
4. Lectura de indicadores · 5. Gráficos · 6. Escenarios · 7. Qué vigilar · 8. Riesgos y supuestos

`assets/estructura.md` es la misma estructura en texto plano, para leerla rápido o editar
contenido, pero **el entregable siempre sale del HTML** — es el que trae el formato.

## Procedimiento

### 1. Leer el texto crudo y extraer

Mapear cada afirmación del usuario a su sección. El orden en que él lo escribió no importa; el
orden del informe sí. Es habitual que el texto crudo traiga contexto y escenarios mezclados y la
conclusión al final — en el informe la conclusión va primera.

### 2. Auditar lo que falta — antes de escribir nada

Recorrer esta lista y anotar cada hueco. **No se completa inventando.**

| Dato | Regla |
|---|---|
| Precio actual | Obligatorio |
| Precio de cada nivel nombrado | Obligatorio. Un nivel sin número no entra a la tabla |
| Nivel de invalidación | Obligatorio, y numérico |
| Horizonte temporal | Obligatorio (semanas / meses) |
| Valor de cada indicador que aparece en los gráficos | Obligatorio: si está en la captura, va leído en la tabla |
| Probabilidades de los escenarios | Suman 100% |
| Objetivos al alza y a la baja | Ambos, no solo el que favorece la tesis |
| Fecha de earnings (si es acción) | Verificar, no estimar |

Todo hueco se escribe en el Doc como `[COMPLETAR: …]` resaltado, y se le reporta al usuario en la
respuesta del chat, agrupado y en orden de importancia.

### 3. Traducir la jerga

El cliente no es trader. Cada término técnico lleva una aclaración de media línea la primera vez
que aparece: "la EMA 200 semanal (el promedio de precio de las últimas 200 semanas, que suele
funcionar como piso)". Si una frase del texto crudo no se entiende sin saber leer un gráfico, se
reescribe.

### 4. Armar el HTML

Copiar `assets/plantilla.html` al scratchpad, reemplazar los placeholders y
ajustar el color al sesgo: verde `#1E7A4D` compra, rojo `#B03A2E` venta, gris `#5A6B7C` neutral.
Si el sesgo es venta, se invierten los colores de los dos bloques de escenarios. Borrar la sección
"Cómo usar esta plantilla" — esa nunca va en un entregable.

Filas que no se usan: se borran, no se dejan vacías. Una tabla con la mitad de las celdas en `[ ]`
se ve peor que una tabla más corta.

### 5. Publicar en Drive

`mcp__claude_ai_Google_Drive__create_file` con `contentMimeType: "text/html"` y el HTML en
`textContent`. Título: `Análisis [TICKER] — [AAAA-MM-DD] — [Cliente]`.

**Límite del conector:** `update_file` solo cambia título y carpeta, **no el contenido**. No se
puede reescribir un Doc existente. Cada revisión es un Doc nuevo; si el usuario quiere conservar
la URL anterior, la vía es que él copie y pegue el contenido del nuevo al viejo.

### 6. Cerrar

En el chat, entregar:
- El link del Doc.
- La lista de `[COMPLETAR]` pendientes, agrupada.
- Recordatorio de pegar las capturas en los dos recuadros punteados y escribir los epígrafes.
- Si el análisis original tenía huecos de razonamiento (no de datos) —una afirmación direccional
  sin invalidación, un indicador mostrado y no leído, una recomendación sin instrucción de
  ejecución— señalarlos. Es la parte de más valor de la skill: el formato lo copia cualquiera.

## Límites duros

- **Nunca inventar un número.** Ni precios, ni niveles, ni valores de indicadores, ni
  probabilidades, ni fechas de earnings. Un dato inventado en un informe que va a un cliente es
  peor que un `[COMPLETAR]` visible. Vale para datos aproximados y para "ejemplos ilustrativos".
- **Nunca cambiar la tesis del usuario.** Si el sesgo parece mal fundado, se le dice en el chat;
  el informe sale con lo que él decidió.
- **El disclaimer del pie no se saca nunca.** El informe no es asesoramiento financiero
  matriculado, y el pie es lo que lo deja por escrito.
- **No consultar precios en la web para rellenar huecos** salvo que él lo pida explícitamente. Un
  precio desactualizado en un entregable es un error del que responde él.

## Checklist antes de entregar

- [ ] Ningún corchete ni resaltado amarillo sin resolver (o todos reportados al usuario)
- [ ] Todo nivel nombrado tiene precio
- [ ] Hay una condición de invalidación numérica
- [ ] Las probabilidades suman 100%
- [ ] Cada indicador de los gráficos está leído en la tabla
- [ ] Cada término técnico está traducido en su primera aparición
- [ ] La sección "Cómo usar esta plantilla" está borrada
- [ ] El disclaimer está
- [ ] 1-2 páginas + gráficos
