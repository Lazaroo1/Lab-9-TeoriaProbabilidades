# Laboratorio 9 — MM3014 Teoría de Probabilidades
**Biancka Raxón (24960) · Lázaro Díaz (24713)**

Simulación del proceso de llenado del álbum Panini del Mundial FIFA 2026 mediante técnicas de Monte Carlo.

---

## Descripción

El álbum consta de **980 estampas** distintas. Cada sobre contiene **7 estampas** (todas distintas dentro del mismo sobre). Se asume distribución uniforme e independiente entre sobres.

---

## Archivos

| Archivo | Descripción |
|---|---|
| `lab9-24960-24713.ipynb` | Notebook con todas las simulaciones de la Etapa 5 (álbum real N = 980) |
| `Lab9_Etapa5.pdf` | Informe con resultados, gráficas y reflexiones de la Etapa 5 |
| `README.md` | Este archivo |

---

## Etapa 3 — Presupuesto y costo (N = 100)

Parámetros: N = 100, S = 7, R = 10,000, semilla 2026.

Simula tres estrategias de compra con presupuesto de Q 1,000:
- **Sobres sueltos** a Q 9.50 c/u (máx. 105 sobres)
- **Caja** de 104 sobres a Q 975
- **Estrategia mixta**: caja + sobres sueltos con el presupuesto restante

Responde tres preguntas de análisis sobre máximos comprables, conveniencia de la caja y estrategia óptima.

---

## Etapa 4 — Intercambio de repetidas (N = 100)

Parámetros: N = 100, S = 7, R = 10,000, semilla 2026.

### Parte A
Simula el proceso hasta completar el álbum para K = 1, 2, 5, 10. Calcula media, desviación estándar y reducción porcentual respecto al caso sin intercambio. Genera histogramas superpuestos.

### Parte B
Para cada K y cada M ∈ {20, 25, …, 70}, estima la probabilidad de completar el álbum con exactamente M sobres. Genera curva de probabilidad vs M e identifica los umbrales del 50 %, 75 % y 90 %.

> **Nota:** la Parte B puede tardar ~7 minutos con R = 10,000. Para pruebas rápidas bajar a R = 1,000.

---

## Etapa 5 — Álbum real (N = 980)

Parámetros: N = 980, S = 7, R = 1,000, semilla 2026.

Se usan menos repeticiones porque cada simulación es ~10× más costosa que con N = 100.

### Preguntas simuladas

| # | Pregunta | Temática |
|---|---|---|
| P1 | ¿Cuántos sobres y cuánto cuesta completar el álbum? Comparar con valor teórico. | Sobres esperados |
| P2 | ¿Cuál es la probabilidad de completarlo con Q 10,000 y con Q 15,000? | Presupuesto fijo |
| P3 | ¿Cuántas cajas se necesitan? ¿Conviene vs sobres sueltos? | Cajas vs sueltos |
| P4 | Con K = 4, ¿cuántos sobres y quetzales se ahorran? | Intercambio de repetidas |
| P5 | ¿Qué reduce más sobres: subir S de 7 a 8, o aplicar K = 4? | Comparación de estrategias |

### Resultados principales

| Métrica | Valor |
|---|---|
| E[sobres] sin intercambio | 1,045 |
| Costo esperado sin intercambio | Q 9,931 |
| Prob. completar con Q 10,000 | 60.6 % |
| Prob. completar con Q 15,000 | 98.7 % |
| E[cajas] necesarias | 10.6 |
| E[sobres] con K = 4 | 258 (−75 %) |
| Ahorro con K = 4 | Q 7,477 |

---

## Cómo ejecutar

El notebook está diseñado para Google Colab. Abrirlo y ejecutar todas las celdas en orden — no requiere instalar nada adicional (numpy y matplotlib vienen incluidos).

```python
# Semilla usada en todas las simulaciones
np.random.seed(2026)
```

Para correr localmente:

```bash
pip install numpy matplotlib jupyter
jupyter notebook lab9-24960-24713.ipynb
```
