# Análisis Técnico — [ACTIVO] ([TICKER])

_El entregable sale de `analisis-activo.html` — ese trae el formato y es el que sube la skill `informe-analisis`. Este `.md` es la misma estructura en texto plano, para leerla rápido o editar contenido._

| Campo | Dato |
|---|---|
| Activo | [Nombre completo] |
| Ticker / mercado | [TICKER — NASDAQ / NYSE / Binance / …] |
| Tipo | [Acción / Cripto / Índice / FX / Commodity] |
| Fecha del análisis | [AAAA-MM-DD] |
| Precio al momento del análisis | [USD X] |
| Temporalidad principal | [Semanal] |
| Temporalidades de apoyo | [Diaria / Mensual] |
| Horizonte del análisis | [Semanas / meses — decir cuántos] |
| Preparado para | [Nombre] |
| Analista | Mateo Ulla |

---

## 1. Conclusión

**Sesgo: [COMPRA / NEUTRAL / VENTA]**

[Una frase, sin jerga. Qué está pasando y qué implica para el que lee.]

**Cómo se ejecuta:** [A mercado ahora / esperar el toque de [nivel] / escalonado en [zona] / no hacer nada todavía.]

**Se invalida si:** [condición numérica y explícita — ej. "cierre de vela semanal por debajo de USD X"].

> Si el cliente lee solo esta sección, ya sabe qué hacer. Todo lo de abajo es el respaldo.

---

## 2. Contexto — dónde está el precio en la película

- **Tendencia primaria (macro):** [alcista / bajista / lateral, desde cuándo]
- **Fase actual:** [corrección dentro de tendencia / rango / ruptura / reversión]
- **Recorrido reciente:** [de dónde vino el precio y cuánto corrigió, en % y en fechas]
- **Cambios desde el análisis anterior:** [si es un seguimiento; si es el primero, borrar esta línea]

---

## 3. Niveles clave

Cada nivel necesita **un número** y **al menos dos confluencias**. Sin precio no es un nivel, es una opinión.

| Nivel | Precio | Tipo | Confluencias (por qué importa) |
|---|---|---|---|
| [Soporte principal] | [USD X] | Soporte | [EMA 200 semanal + zona de alto volumen + Fib 0,5] |
| [Soporte secundario] | [USD X] | Soporte | [ ] |
| [Resistencia / máximo previo] | [USD X] | Resistencia | [ ] |
| [Objetivo alcista] | [USD X] | Objetivo | [ ] |

---

## 4. Lectura de indicadores

| Indicador | Lectura actual | Qué implica |
|---|---|---|
| EMA 20 (semanal) | [USD X — precio por encima/debajo] | [ ] |
| EMA 50 (semanal) | [USD X] | [ ] |
| EMA 200 (semanal) | [USD X] | [ ] |
| RSI (semanal) | [valor] | [sobrecompra / sobreventa / neutral] |
| Divergencias (MarketCipher B) | [alcista / bajista / ninguna] | [ ] |
| Perfil de volumen | [zona de alto volumen en USD X–Y] | [ ] |
| Retroceso de Fibonacci | [0,5 en USD X — desde el mínimo A al máximo B] | [ ] |

> Regla: si un indicador aparece en el gráfico, aparece en esta tabla. Un indicador que se muestra y no se lee es ruido.

---

## 5. Gráficos

**Gráfico 1 — [qué muestra]**
`[pegar imagen]`
*Epígrafe: [1-2 líneas — qué está marcado y dónde tiene que mirar el lector.]*

**Gráfico 2 — [qué muestra]**
`[pegar imagen]`
*Epígrafe: [1-2 líneas.]*

> Regla: un gráfico sin epígrafe no se manda. El cliente no sabe qué es la línea violeta.

---

## 6. Escenarios

### Escenario principal — [nombre corto] · probabilidad estimada: [X%]

- **Disparador:** [qué tiene que pasar para que arranque]
- **Desarrollo esperado:** [ ]
- **Objetivos:** [USD X, y si sigue, USD Y]
- **Qué lo confirma:** [señal concreta y observable]

### Escenario alternativo — [nombre corto] · probabilidad estimada: [X%]

- **Disparador:** [ ]
- **Desarrollo esperado:** [ ]
- **Objetivos a la baja:** [USD X]
- **Qué lo confirma:** [ ]

> Las probabilidades suman 100%.

### Invalidación de la tesis

- **Nivel:** [USD X]
- **Qué significa romperlo:** [ ]
- **Qué haría en ese caso:** [salir / reducir / esperar / re-evaluar en tal nivel]

---

## 7. Qué vigilar

1. [Señal concreta y verificable]
2. [ ]
3. [ ]

---

## 8. Riesgos y supuestos

- **Qué podría estar mal en esta lectura:** [el supuesto más frágil del análisis]
- **Eventos de calendario:** [earnings, datos macro, desbloqueos de tokens, con fecha]
- **Liquidez / contexto de mercado:** [ ]

---

*Análisis técnico con fines informativos y educativos. No es recomendación de inversión ni asesoramiento financiero. Toda decisión de compra o venta es responsabilidad de quien la toma. El desempeño pasado no garantiza resultados futuros.*

---
---

# Cómo usar esta plantilla

**Borrar esta sección entera antes de enviar.**

1. **Se completa de arriba hacia abajo, pero la Conclusión se escribe al final.** No se sabe cuál es el titular hasta haber mirado los niveles y los escenarios.
2. **Todo lo que está entre corchetes se reemplaza o se borra.** Si quedó un corchete en el documento, no se manda.
3. **Ningún nivel sin número.** "Zona de soporte" no es un dato; "USD 4.850–4.980" sí.
4. **Toda afirmación direccional lleva su invalidación.** Si no se puede decir a qué precio la tesis está equivocada, la tesis no está terminada.
5. **Nada de jerga sin traducir.** La primera vez que aparece un término (EMA, Fibonacci, divergencia), va una aclaración de media línea entre paréntesis. El cliente no es trader.
6. **Largo objetivo: 1-2 páginas + los gráficos.** Si se pasa, sobra contexto, no faltan datos.
7. **Secciones opcionales según el caso:** si el activo es una acción, la sección 8 lleva earnings; si es cripto, lleva desbloqueos y dominancia. Si una fila de la tabla de indicadores no se usó en el gráfico, se borra la fila.

**Nombre del archivo al copiar:** `Análisis [TICKER] — [AAAA-MM-DD] — [Cliente]`
