# START HERE — LocalHost S.R.L. en 10 minutos

> **Para compañeros nuevos. Si solo tenés 2 minutos, leé únicamente la sección 1 y la FAQ relámpago (sección 6).**

---

## 1. En 30 segundos

**LocalHost S.R.L. — *Tu nube, en tu casa* — te instala tu nube privada en tu domicilio en 48 h.** Un mini-servidor con las apps que elijas (fotos, archivos, pelis, contraseñas) para dejar de pagar 4–7 suscripciones en dólares.

El **sistema a construir es LocalHost Nexus**: baja la instalación de 8 h a 90 min y permite cuidar 150 clientes sin sumar técnicos. Sin Nexus, no hay negocio.

- **Hardware:** tuyo desde día 1 (compra 100%) o en **comodato** (nuestro, con Care obligatorio 12 meses, lo comprás cuando quieras).
- **Datos:** siempre tuyos. LocalHost solo ve salud del equipo, nunca contenido.
- **Abono Care:** monitoreo + soporte proactivo. Sin abono, soporte por ticket a USD 80/h.

**¿Por qué existe este documento en la materia?** Es la empresa ficticia que justifica el sistema. Todo el análisis (procesos, ingresos, Canvas) cuelga de acá.

---

## 2. Mapa de lectura — elegí tu tiempo

| Si tenés…         | Hacé esto                                                                                    | Archivos                                        |
| :---------------- | :------------------------------------------------------------------------------------------- | :---------------------------------------------- |
| **2 min**         | Esta página §1 + §6 (FAQ relámpago)                                                          | Solo este `START-HERE.md`                       |
| **10 min**        | Este archivo completo + abrí el Canvas visual en el navegador                                | `localhost-business-model-canvas.html`          |
| **30 min**        | Leé `localhost-documento-y-canvas.md` lineal (§3, §6.1, §7.4, §10.1 son los diagramas clave) | Documento (860 líneas, tablas reemplazan texto) |
| **Para exponer**  | §7 de esta guía (guion 5 min) + Canvas impreso A3                                            | Esta guía + Canvas HTML                         |
| **Para estudiar** | `cuestionario-feynman.md` — 36 preguntas, método Feynman                                     | Cuestionario                                    |

**Regla anti-abrumo:** cada sección del documento arranca con la idea clave. No hace falta leerlo entero para entender el sistema.

---

## 3. Las 3 piezas — dónde vive cada cosa

```text
[Tu casa / Oficina]              [Taller LocalHost]         [Tu celular / Web]
 ┌─────────────────┐              ┌──────────────┐           ┌─────────────┐
 │ Servidor cliente│◄────────────►│   Central    │           │   Portal    │
 │ Nextcloud etc.  │   Agente     │  (solo salud)│◄──────────│  (tickets,  │
 │ Datos privados  │──reporta cada│  Panel verde │  ticket   │   facturas) │
 └─────────────────┘   5 min      └──────────────┘  +contexto └─────────────┘
        │  Datos 100% privados nunca salen de tu casa
        └─ Si se corta internet, sigue andando en red local
```

| Pieza | Dónde vive | Quién la ve | Qué ve |
| :--- | :--- | :--- | :--- |
| **Servidor** | Domicilio (Opción A) o rack LocalHost (Opción B) | Cliente | Tus datos. 100% privado |
| **Agente** | En cada servidor | Servicio automático | Reporta salud (disco, backup, uptime). Si no hay Care, se desinstala |
| **Central** | Taller LocalHost | Solo equipo LocalHost | Semáforo verde/amarillo/rojo por cliente. Nunca contenido |
| **Portal** | Web | Cliente | Estado, tickets, facturas. 3 botones, sin config técnica |

> **Garantía clave:** Central nunca ve contenido. Acceso remoto solo con tu aprobación explícita desde el Portal, queda registrado y es temporal. Ver §8 del documento.

---

## 4. Las 2 puertas — cómo entra y cómo se va el cliente

```text
ENTRADA                          PERMANENCIA              SALIDA
┌──────────────┐                 ┌─────────┐              ┌──────────────┐
│ Puerta A     │  entrada        │  Care   │   ¿Se quiere│ A1 Compra    │
│ COMODATO     │  USD 250-400    │ 12 meses│   ir? ─────►│ disco (Tabla │
│ Equipo nuestro│ + Care 12m     │ obligatorio             │ residual)    │
│ Agente ON    │  obligatorio    │ USD25-60│              │ A2 Transfiere│
└──────────────┘                 └─────────┘              │ y devuelve   │
┌──────────────┐                 ┌─────────┐              │ B  Borrado   │
│ Puerta B     │  1 pago o       │  Care   │              │ NIST +       │
│ COMPRA 100%  │  cuotas MP      │ opcional│              │ certificado  │
│ Equipo tuyo  │  BYO auditado   │ (recomendado)          └──────────────┘
│ Agente ON si │  si ya tenés HW │ Agente ON si hay Care
│ hay Care     │                 └─────────┘
└──────────────┘
```

**Tabla residual (si compra el disco en comodato):** 100% día 1 → 66% a 12 meses → 33% a 24 meses → 10% a 36+ meses. Alternativas: transferir a disco propio (sin costo) o borrado certificado NIST.

---

## 5. Por qué este modelo — las 5 decisiones en 1 línea cada una

| # | Decisión | Qué cambia |
| :--- | :--- | :--- |
| 1 | **Care obligatorio en comodato** | 100% de comodatos con abono. Antes muchos se iban sin abono y no había recurrente |
| 2 | **Backup externo cifrado +USD 10–15/mes** | Tu clave, en nuestro taller. Ingreso nuevo casi sin costo |
| 3 | **Foco 85–90% B2B** | Un hogar paga USD 30 y discute precio. Un estudio paga USD 80–400/mes en SaaS y ve ROI claro |
| 4 | **Desarrollo a medida USD 800 + USD 20/mes** | Antes USD 1500 una vez. Ahora recurrente + fideliza 12+ meses |
| 5 | **Prepago anual USD 250–550 (2 meses gratis)** | Cliente ahorra 2 meses, nosotros cobramos caja adelantada para stock |

**Resultado:** mix 40% HW / 60% abonos, facturación **USD 160–190k/año**.

---

## 6. FAQ relámpago — 6 preguntas que te van a hacer

**¿No es lo mismo que un NAS de MercadoLibre?**
No. El NAS lo comprás, instalás y mantenés vos. LocalHost te lo entrega llave en mano, monitoreado, con apps a medida y soporte humano local.

**¿Por qué no vendemos una sola cosa para todos?**
Packs 3+3 base personalizable: **Negocio** (Nextcloud+OnlyOffice, Vaultwarden, Paperless) y **Hogar** (Immich, Jellyfin, Nextcloud). Cada cliente pide lo que necesita.

**¿Qué ve LocalHost de mis datos?**
Nada. Solo salud: "disco 80% lleno, copia OK". Cuatro garantías: arquitectura (Central no lee contenido), acceso solo con tu aprobación, servidor en tu casa, y borrado certificado si te vas.

**¿Qué pasa si me quiero ir a los 14 meses?**
Tres opciones: comprás el disco a residual (66%→33%), transferís a tu disco y devolvés el nuestro, o pedís borrado NIST y te vas sin nada.

**¿Y si no tengo lugar en casa?**
Opción B: queda en nuestro taller con fibra y energía 24/7, disco cifrado con tu clave. +USD 15–25/mes. Migrás a Opción A cuando quieras.

**¿Cuándo recupero la inversión?**
8–14 meses vs. suscripciones. Familia 2TB: ~12 meses. Estudio 4TB: ~14 meses. Después es ahorro neto.

*FAQ completa (10 preguntas): `localhost-documento-y-canvas.md` §11.*

---

## 7. Guion de 5 minutos — para exponer sin leer

> Copiá y pegá tal cual. Está cronometrado.

**Min 0:00–0:40 — Qué hace LocalHost (1 frase + dolor)**
"LocalHost te instala tu nube privada en tu casa en 48 h para dejar de pagar 4–7 suscripciones en dólares. Un estudio que hoy paga USD 80/mes en Drive/Dropbox/Slack recupera la inversión en 14 meses y después ahorra USD 540/año."

**Min 0:40–1:30 — Por qué necesitamos Nexus (problema operativo)**
"Hoy cada instalación nos lleva 8 h artesanal por SSH, sin estándar, sin monitoreo. Máximo 8 instalaciones/mes, 25% de retrabajo. Nexus baja eso a 90 min y nos deja cuidar 150 clientes con el mismo equipo de 5."

**Min 1:30–2:30 — Las 3 piezas (mostrá diagrama §6.1)**
"Central en nuestro taller (solo salud), Agente en cada servidor (reporta cada 5 min, nunca contenido), Portal para el cliente (3 botones). Si se corta internet, el servidor sigue andando en red local."

**Min 2:30–3:30 — Las 2 puertas + 5 decisiones (mostrá Canvas)**
"Dos formas de entrar: comodato con Care obligatorio 12 meses (entrada USD 250–400) o compra 100% con Care opcional. Cinco decisiones llevan el mix a 40/60 y la facturación a USD 160–190k: Care obligatorio, backup cifrado, foco B2B, desarrollo con mantenimiento y prepago anual."

**Min 3:30–4:30 — Privacidad + salida (objeción más dura)**
"Cuatro garantías: Central no ve contenido, acceso solo con tu aprobación y registro, servidor en tu casa, borrado NIST si te vas. Si te vas, comprás el disco a residual, transferís o pedís borrado. BYO auditado si ya tenés hardware."

**Min 4:30–5:00 — Cierre (qué entregamos en la materia)**
"MVP en 3 meses: relevamiento + presupuestador + preparación de 1 pack + panel semáforo simulado. Canvas impreso A3 y documento quedan como única fuente de verdad."

---

## 8. Qué hacer ahora — checklist para el equipo

- [ ] Cada uno lee esta guía (10 min) y abre el Canvas HTML.
- [ ] Si van a exponer, ensayen el guion de §7 una vez en voz alta (cronómetro).
- [ ] Dudas → FAQ §6 de esta guía, luego §11 del documento. Si sigue sin cerrar, issue con `ruta/archivo.md`.

---

## 9. Dónde está cada cosa

```text
localhost/
├── README.md                              # Este es el índice — qué es?
├── START-HERE.md                          # Esta guía — 10 min
├── localhost-documento-y-canvas.md        # Documento único
├── localhost-business-model-canvas.html   # Canvas A3
├── cuestionario-feynman.md                # 36 preguntas Feynman
└── consignas-para-definir-la-empresa.pdf  # Consigna cátedra (no se toca)
```

---
*Hecho para que no tengas que leer 860 líneas para entender el sistema. Si esta guía no te alcanza, el documento tiene el detalle.*
