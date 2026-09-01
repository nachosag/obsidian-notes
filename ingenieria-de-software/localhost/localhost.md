# LocalHost S.R.L. — Síntesis para la cursada

> **Tu nube, en tu casa. En 48 h, sin suscripciones en dólares.**
> Este doc es el resumen corto del documento integrado. Si leés solo esto, entendés el 90% para la cursada y para exponer. El doc completo queda como referencia.

**Empresa ficticia:** LocalHost S.R.L. (5 estudiantes UNGS, Buenos Aires AMBA, 2026)  
**Sistema a desarrollar:** LocalHost Nexus — plataforma que automatiza instalar y cuidar servidores privados a medida.  
**Doc completo:** `localhost-documento-y-canvas.md` · **Canvas visual A3:** `localhost-business-model-canvas.html`

---

## En 30 segundos — si solo leés esto, alcanza

**LocalHost te instala tu nube privada en tu casa u oficina en 48 h.** Un mini-servidor con las apps que vos elijas (fotos, archivos, pelis, contraseñas) y dejás de pagar 4 a 7 suscripciones en dólares.

- **El hardware puede ser tuyo día 1 o quedar en comodato** y lo comprás cuando quieras (ver tabla de depreciación abajo).
- **Tus datos son siempre tuyos.** LocalHost solo ve salud del equipo, nunca contenido.
- **Nexus baja la instalación de 8 h a 90 min** y permite cuidar 150 clientes sin sumar técnicos. Ese es el motivo del sistema en la materia.

---

## Cómo usar este resumen

| Si tenés…    | Leé…                                     |
| :----------- | :--------------------------------------- |
| 1 min        | Solo "En 30 segundos" de arriba          |
| 5 min        | + secciones 1 a 6 (este doc completo)    |
| 15 min       | + FAQ y tabla del Canvas (sección 7 y 8) |
| Para exponer | Este doc + imprimir el Canvas A3         |

---

## 1. ¿Qué es LocalHost y a quién le vende?

**Industria:** Tecnología / Servicios Informáticos y Telecomunicaciones. Intersección de Electrónica (hardware), Telecom (conectividad segura) y Software (apps open source).

| Dato                         | Resumen                                                                                                                                                                          |
| :--------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Qué vende**                | Servidor privado a medida + instalación llave en mano + cuidado (abono)                                                                                                          |
| **Equipo**                   | 5 socios, 6 funciones (Gerencia, Operaciones x2, Soporte, Comercial, Admin + los 5 como Dev)                                                                                     |
| **Taller**                   | CABA/AMBA, 30–40 m², stock 5–8 equipos. Instalación AMBA presencial, interior con partner local                                                                                  |
| **Mercado principal (70%)**  | Negocios que sufren suscripciones en USD: estudios jurídicos/contables, fotografía, productoras, agencias (3–30 personas, pagan USD 40–400/mes en nube)                          |
| **Mercado secundario (30%)** | Hogares prosumers con 1–2 TB de fotos/archivos                                                                                                                                   |
| **Ventaja**                  | Únicos en Argentina con combo llave en mano + local + humano + a medida. Competencia: Synology/QNAP (solo venden aparato), Big Tech (alquilan nube), Umbrel/CasaOS (DIY técnico) |

> **Dato verosímil para defender:** facturación proyectada 12 meses USD 120–150k (70% instalaciones, 30% abonos).

---

## 2. El problema real (por qué existe Nexus)

**Para el cliente:**
Paga USD 40–400/mes en 4–7 suscripciones (caso testigo Nate Gentile: €33k en 2 años), no controla sus datos, y armar su propio servidor es muy técnico (Docker, puertos, backups).

**Para LocalHost (el disparador del sistema):**

| Problema operativo | Impacto |
| :--- | :--- |
| Instalación artesanal 6–10 h | Máximo 8 instalaciones/mes |
| Sin estándar | 25% de retrabajo por configs distintas |
| Sin monitoreo | Se enteran cuando el cliente llama sin espacio |
| Sin historial | No hay base de conocimiento |

**Objetivo del sistema:** bajar de 8 h a **90 min** por instalación y poder monitorear **150 clientes en 12 meses**.

---

## 3. LocalHost Nexus en 3 piezas

> Dónde vive cada cosa y quién ve qué — la figura que más pregunta el profesor.

| Pieza | Dónde vive | Quién la usa | Qué ve |
| :--- | :--- | :--- | :--- |
| **LocalHost Central** | Oficina LocalHost (SaaS interno) | Equipo LocalHost | Solo salud y gestión. Nunca contenido |
| **LocalHost Agente** | En cada servidor del cliente | Servicio automático | Reporta cada 5 min (disco, CPU, backup). Si cae internet, el servidor sigue andando |
| **Portal Cliente** | Web/app simple | Cliente final | 3 botones: Estado, Soporte, Facturas. No configura nada técnico |

**Regla de oro:** Central **nunca** ve fotos, docs ni contraseñas. Acceso remoto solo vía WireGuard/Tailscale con permiso explícito, temporal y auditado.

**Módulos clave (los 7, en 1 línea c/u):** Catálogo de apps en 1 clic · Relevamiento y presupuestador con ROI vs suscripciones · Orquestador que graba imagen + inyecta perfil · Monitoreo semáforo verde/amarillo/rojo · Tickets con contexto · Facturación/AFIP/MercadoPago · Desarrollo a medida (Paperless+AFIP, bots, n8n).

---

## 4. Packs 3+3 — todo es personalizable

Pedís un pack base y sumás apps sueltas (ej. "Negocio + Immich").

| Pack Negocio (confidencialidad) | Reemplaza a | Pack Hogar (recuerdos/entretenimiento) | Reemplaza a |
| :--- | :--- | :--- | :--- |
| **Nextcloud + OnlyOffice** | Drive / Dropbox / M365 | **Immich** | Google Fotos / iCloud (IA local) |
| **Vaultwarden** | 1Password / Bitwarden nube | **Jellyfin** | Netflix / Plex |
| **Paperless-ngx** | Gestión de papeles escaneados | **Nextcloud** | Archivos familiares + backup celus |

---

## 5. Cómo gana plata (modelo híbrido)

> El hardware deja poco margen. El abono deja ~90%. El negocio escala vendiendo abonos.

| Fuente                                     | Modalidad                          | Rango                                                                    | Nota                                                           |
| :----------------------------------------- | :--------------------------------- | :----------------------------------------------------------------------- | :------------------------------------------------------------- |
| **Instalación llave en mano**              | 1 pago o cuotas MercadoPago        | **USD 600–1.800**                                                        | Con comodato: entrada USD 250–400 + cuotas                     |
| **Abono Care** (plan único a medida)       | Mensual, opcional pero recomendado | **USD 25–60/mes** (base ~20 + variables: TB, apps, acceso externo, RAID) | Incluye monitoreo 5 min, updates, 2 h soporte. SLA 24 h        |
| **Hosting Opción B** (en taller LocalHost) | Mensual                            | **+USD 15–25/mes**                                                       | Si no querés el equipo en casa                                 |
| **Seguro hardware**                        | Mensual                            | **+USD 5–8/mes**                                                         | Reposición 72 h con seguro, 5 días sin seguro                  |
| **Desarrollo a medida**                    | Por proyecto                       | **USD 500–3.000**                                                        | Post-instalación (ej. integraciones)                           |
| **Sin abono**                              | Por ticket                         | **USD 80/h**                                                             | Solo 30 días de garantía, sin monitoreo, *best effort* 72–96 h |
| **Descuento telemetría**                   | Mensual                            | **–USD 3–5/mes**                                                         | Si compartís métricas anónimas (opt-in)                        |

**Break-even para el cliente:** recuperás la inversión en **8–14 meses** vs suscripciones (ej. familia 2 TB: ~12 meses, estudio 4 TB: ~14 meses).

---

## 6. Propiedad, salida y privacidad — lo que más objeciones genera

### El equipo

Por defecto es **comodato con opción de compra en cualquier momento**. Si ya tenés equipo, lo auditamos (BYO) y si pasa el checklist, se reutiliza y baja el costo.

| Momento de compra | Pagás | Ejemplo sobre USD 800 |
| :--- | :--- | :--- |
| Día 1 | 100% | USD 800 — sos dueño ya |
| 12 meses | 66% | USD 528 |
| 24 meses | 33% | USD 264 |
| 36+ meses | 10% simbólico | USD 80 |

Presupuesto detalla Disco (ej. USD 200) y Resto (mini-PC+UPS, ej. USD 600) por separado, cada uno con su depreciación lineal.

### Si te querés ir — elegís vos, sin letra chica

| Opción | Qué hacés | Qué recibís |
| :--- | :--- | :--- |
| **A1 — Comprás el disco** | Pagás residual según tabla y te llevás el disco | Tu disco + datos intactos |
| **A2 — Transferís y devolvés** | Copiás tus datos a un disco propio, devolvés el original | Tus datos en tu disco, costo cero |
| **B — Borrado certificado** | Pedís borrado seguro NIST 800-88 | Certificado de borrado, hardware vuelve a stock |

### Privacidad: por qué monitorear no rompe la promesa

- Solo reportamos **salud** ("62% disco usado, 99.2% uptime"), nunca contenido.
- Descuento por **acceso a datos personales: descartado** (rompe propuesta de valor y Ley 25.326). Alternativa: **descuento USD 3–5/mes por telemetría anónima**, agregada en origen, opt-in revocable en 1 clic.
- **4 garantías:** arquitectura (Central no ve contenido) + acceso con tu permiso auditado + disco en tu casa (anda sin internet) + contrato + borrado NIST 800-88.
- Disco cifrado LUKS. Por defecto vos cuidás la clave. Opcionales con consentimiento: sobre sellado en caja fuerte o Shamir 2-de-3 (cliente/LocalHost/contacto confianza).

---

## 7. Canvas en 1 tabla — para copiar a la presentación

| Bloque | Idea clave en 1 línea |
| :--- | :--- |
| **1. Segmentos** | Negocios 3–30 pers. que sangran en suscripciones (70%) + hogares tech (30%) |
| **2. Propuesta valor** | "Tu nube privada en 48 h, a medida, llave en mano, local y humana" — 40–60% ahorro + control |
| **3. Canales** | Web/simulador ahorro → visita relevamiento → presupuesto PDF → instalación + capacitación → monitoreo/WhatsApp/Portal |
| **4. Relación clientes** | Asistencia personal + soporte proactivo + comunidad + co-creación (votan próximo pack) |
| **5. Ingresos** | Instalación + Care mensual + hosting B + seguro + desarrollo a medida + ticket sin abono |
| **6. Recursos clave** | Home-lab + stock rotativo (comodato), Nexus como activo intelectual, 5 socios devs |
| **7. Actividades clave** | Relevamiento/consultoría, ensamblado automatizado, instalación, monitoreo/post-venta, curaduría apps |
| **8. Asociaciones** | Hardware (Beelink/Seagate/APC), upstream OSS (Nextcloud/Immich...), Tailscale/WireGuard, MercadoPago/AFIP, partners interior |
| **9. Costes** | Fijos: equipo + home-lab. Variables: hardware/viáticos. Economía escala: 8 h → 1.5 h + BYO auditado |

> Canvas visual A3 imprimible: `localhost-business-model-canvas.html`

### 5 palancas para ganar más (resumen)

1. **Comodato + Care 12 meses con 10% off** → sube abono del 30% al 80% de clientes.
2. **Backup externo cifrado +USD 10–15/mes** → ingreso nuevo casi sin costo.
3. **Foco B2B** (menos clientes, más ticket) en vez de hogares que discuten USD 30.
4. **Desarrollo a medida con mantenimiento USD 20/mes** → renta recurrente.
5. **Care anual con 2 meses gratis** → caja adelantada + retención.

Las 1 y 2 son cambios chicos y las que más suman.

---

## 8. FAQ express — lo que va a preguntar el profe/compañeros

**¿Qué es Nexus para el cliente?** No lo ve. Es el sistema interno que hace que te instalen el aparatito y te lo cuiden. Vos solo usás tus apps.

**¿Por qué monitorear si venden privacidad?** Porque es como el service del auto: miramos "cuánto disco te queda", no tus fotos. Sin eso no podemos avisarte antes de que falles. Sin abono, no monitoreamos.

**¿Cómo sabe el cliente que no lo espiamos?** Arquitectura separada + acceso solo con su permiso y auditado + disco en su casa + contrato + borrado certificado.

**¿El abono es obligatorio?** No, pero sin él tenés solo 30 días de garantía y luego USD 80/h sin SLA. Con Care tenés monitoreo, updates y reposición garantizada.

**¿Y si no tengo lugar?** Opción B: tu servidor (sigue siendo tuyo) queda en nuestro rack con fibra/energía 24/7 por +USD 15–25/mes. Disco cifrado, clave tuya.

**¿Cuándo recupero la plata?** Entre 8 y 14 meses según perfil. Después es ahorro puro. El presupuestador te muestra tu break-even exacto.

---

## Checklist — ¿entendiste el doc?

- [ ] Podés explicar en 1 frase qué vende LocalHost y en 1 frase qué hace Nexus
- [ ] Sabés decir por qué el hardware en comodato baja la barrera de entrada de USD 1.500 a USD 250–400
- [ ] Podés dibujar de memoria Central → Agente → Servidor → Portal y la regla "solo salud"
- [ ] Sabés las 3 opciones de salida (A1, A2, B) y que BYO no entra en comodato
- [ ] Podés defender por qué se descartó el descuento por datos personales y se usa telemetría anónima
- [ ] Ubicás los 5 ingresos y por qué el abono es el que escala

---

## Qué no está acá y dónde buscarlo

| Si necesitás…                               | Abrí…                    |
| :------------------------------------------ | :----------------------- |
| Diagrama flujo salida y depreciación exacta | Doc completo §7.2 y §7.4 |
| Tabla BYO auditado (CPU/RAM/SMART)          | Doc completo §7.3        |
| Métricas anónimas concretas y anonimización | Doc completo §9          |
| Diagrama ingresos y tabla detallada         | Doc completo §10.1–10.2  |
| Guion de 5 min para exponer                 | Doc completo §12         |
| Naming descartado (Own I.T., OwnStack…)     | Anexo A                  |

> **Nota:** todos los datos son ficticios pero verosímiles (mercado argentino 2025–26). Nexus es implementable como MVP en 3 meses: relevamiento + presupuestador + 1 pack + panel monitoreo simulado.
