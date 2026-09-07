# LocalHost S.R.L. — Punto de entrada

> **Si es tu primera vez acá, empezá por `START-HERE.md` (10 minutos). Todo lo demás es profundización.**

## Qué es esto

**LocalHost S.R.L. — *Tu nube, en tu casa*.** Instalamos un mini-servidor en el domicilio del cliente (48 h) con apps open source a medida (Nextcloud, Immich, Jellyfin, Vaultwarden, Paperless) para reemplazar 4–7 suscripciones en dólares. El sistema que vamos a construir es **LocalHost Nexus**: baja la instalación de 8 h a 90 min y permite cuidar 150 clientes sin sumar técnicos.

## Cómo leerlo sin abrumarte

| Tiempo | Qué hacer |
| :--- | :--- |
| **2 min** | Leé `START-HERE.md` → sección "En 30 segundos" + FAQ relámpago. |
| **10 min** | `START-HERE.md` completo + abrí `localhost-business-model-canvas.html` en el navegador. |
| **30 min** | `localhost-documento-y-canvas.md` lineal. Las tablas y los 3 diagramas Mermaid (§6.1, §7.4, §10.1) reemplazan párrafos largos. |
| **Para exponer** | `START-HERE.md` → "Guion de 5 min" + Canvas impreso en A3. |
| **Para estudiar a fondo** | `cuestionario-feynman.md` — método Feynman en 4 pasos. Si no podés explicarlo simple, no lo entendiste. |

## Estructura

```text
localhost/
├── localhost-documento-y-canvas.md          # Documento integrado (único, ~860 líneas)
├── localhost-business-model-canvas.html     # Lienzo visual A3 imprimible
├── cuestionario-feynman.md                  # 36 preguntas para validar que entendiste
├── START-HERE.md                            # Esta guía — 10 min
├── README.md                                # Este índice
└── consignas-para-definir-la-empresa.pdf    # Consigna cátedra (no se toca)
```

## El modelo en 5 decisiones

El mix objetivo es **40% hardware / 60% abonos** con facturación USD 160–190k/año:

1. **Care obligatorio en comodato** (12 meses) — 100% de comodatos con abono.
2. **Backup externo cifrado** +USD 10–15/mes — ingreso recurrente casi sin costo.
3. **Foco 85–90% B2B** — menos clientes, más valor por cliente (un estudio paga USD 80–400/mes en SaaS).
4. **Desarrollo a medida con mantenimiento** USD 800 + USD 20/mes — convierte one-shot en recurrente.
5. **Prepago anual** USD 250–550 (2 meses gratis) — caja adelantada.

Detalle en `localhost-documento-y-canvas.md` §10.5.

## Para contribuir

- Estás en Obsidian — abre `localhost-documento-y-canvas.md` directo desde el vault.
- Dudas conceptuales → sección 11 (FAQ, 10 preguntas) del documento. Si no está ahí, abrí un Issue con `ruta/archivo.md` + ejercicio.
- No dupliques archivos para versionar. Usa Git (`git log --follow`).

---
*Mantenido por el equipo de 5 (UNGS, Sistemas). Última actualización: 2026-09-07.*
