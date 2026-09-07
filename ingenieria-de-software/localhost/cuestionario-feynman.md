# Cuestionario Feynman — LocalHost S.R.L

> **Objetivo:** Corroborar qué tan claro tenés el proyecto explicándolo simple. Si no podés explicarlo simple, no lo entendiste.
> **Versión:** con las 5 decisiones de rentabilidad aplicadas
> **Cómo usarlo (Método Feynman en 4 pasos):**
>
> 1. Elegí una pregunta y tratá de responderla **en voz alta, como si se la explicaras a alguien que no sabe nada** (tu abuela, un compañero de otra carrera).
> 2. **No mires el documento** la primera vez. Escribí tu respuesta en el espacio `> Tu respuesta:`.
> 3. Después compará con `localhost-documento-y-canvas.md` y marcá qué te faltó. Usá 🟢 (lo expliqué perfecto), 🟡 (me trabé) o 🔴 (no supe).
> 4. Volvé a explicar el punto que marcaste 🟡/🔴 hasta que te salga fluido. Ese es el bache real.

**Tip del Gentleman:** Si usás más de 2 términos técnicos sin explicarlos, reprobaste Feynman. Volvé a empezar.

---

## Nivel 1 — ¿Podés explicárselo a tu abuela? (Concepto)

Si fallás acá, no entendiste el negocio.

**1. En una frase, ¿qué hace LocalHost?**
> Tu respuesta: ofrece un servicio de instalacion y monitoreo de servidores privados para empresas, pymes, oficinas y/o familias. Un servidor privado te permite liberarte de múltiples suscripciones mensuales (SasS) y suplantarlas con alternativas Open Source gratuitas. El ahorro de costos no es el único beneficio, tener tus datos en un servidor privado ofrece privacidad.

**2. ¿Por qué alguien pagaría por esto si ya existe Google Drive y Netflix?**
> Tu respuesta: realmente no se como contestarla

**3. ¿Qué es LocalHost Nexus y por qué no es solo "instalar Nextcloud"?**
> Tu respuesta: LocalHost Nexus es el software central para gestionar nuestros clientes, los servidores, nuestros procesos internos, nuestro stock disponible (tanto hardware como software), etc. Es nuestro centro de operaciones.

**4. Explicá la diferencia entre Opción A y Opción B como si fuera para tu mamá.**
> Tu respuesta: Opción A: el aparatito queda en tu casa, anda aunque se corte internet y nadie más lo toca. Opción B: si no tenés lugar, queda en nuestro taller con luz y fibra 24/7, pero el disco sigue siendo tuyo y cifrado con tu clave — nosotros solo damos energía y estantería, no vemos nada.

**5. ¿Por qué el hardware es en comodato y no lo vendemos de una? ¿Qué gana el cliente y qué ganamos nosotros?**
> Tu respuesta: el hardware es un comodato porque le permite al cliente tener su servidor por un precio muy accesible. LocalHost sigue siendo dueño del hardware y le permite reutilizarlo si el cliente desea irse.

**6. Si tu amigo te dice "es lo mismo que comprar un NAS en MercadoLibre", ¿qué le contestás en 30 segundos?**
> Tu respuesta: El NAS de ML lo tenes que comprar, instalar, configurar y mantener VOS. LocalHost te ofrece un NAS a medida, monitoreado, con las apps que realmente vas a utilizar y vos solo te preocupas por usarlo y disfrutarlo.

**7. ¿Qué son los packs 3+3 y por qué no vendemos una sola cosa para todos?**
> Tu respuesta: Pack Negocio: Nextcloud+OnlyOffice, Vaultwarden, Paperless. Pack Hogar: Immich, Jellyfin, Nextcloud. No vendemos una sola cosa para todos porque existen distintas necesidades. No vendemos una sola cosa para todos porque existen distintas necesidades.

---

## Nivel 2 — ¿Podés defender los números ante el profesor? (Negocio)

Acá te van a matar si dudas.

**8. ¿Cuánto factura LocalHost y por qué cambia el mix?**
> Pista: 40% instalaciones / 60% abonos. ¿De dónde sale la plata ahora?
> Tu respuesta: El 40% de los ingresos provienen de las instalaciones y el 60% restante proviene de los abonos mensuales. Hacer el foco en los abonos le permite a LocalHost ser más rentable. Si solo vivimos de las instalaciones, corremos el riesgo de quiebra.

**9. Explicá las 5 palancas en 1 línea cada una, sin mirar.**
>
> 1. Pack 12m: ofrecemos el hardware como Comodato y Care por 12 meses (con 2 meses de regalo).
> 2. Backup externo: ofrecemos un backup cifrado de los datos del cliente en nuestras oficinas.
> 3. Foco B2B: priorizamos B2B porque son los usuarios que están más atados a SaaS's y que más beneficios pueden sacar de un server privado.
> 4. Mantenimiento: desarrollo de software a medida + integraciones + mantenimiento
> 5. Prepago anual: ofrecemos la posibilidad de pagar 12 meses del abono Care. El cliente recibe 2 meses gratis y LocalHost recibe una suma considerable de capital para financiar sus actividades.

**10. ¿Por qué el foco pasó de 70% negocios a 85-90% B2B? ¿Qué le decís al profesor si te dice que están discriminando a los hogares?**
> Tu respuesta: Porque los negocios son los usuarios más atados a SaaS's y los más beneficiados de un servidor privado. No discriminamos sino que priorizamos.

**11. ¿Cuánto paga un cliente tipo por mes? Armá un presupuesto de ejemplo.**
> Ej: Estudio contable con 4TB + 5 usuarios + acceso externo + backup. ¿Cuánto da?
> Tu respuesta: no nos interesan los numeros concretos.

**12. ¿En cuántos meses recupera la inversión un cliente? ¿Y nosotros cuándo empezamos a ganar de verdad?**
> Tu respuesta: no sé como contestar esto.

**13. ¿Por qué el abono Care deja 90% de margen y el hardware casi nada?**
> Tu respuesta: El margen de ganancia de la venta de hardware es mucho menor en comparación con el del abono Care porque el hardware lo vendemos un ~15% más caro, mientras que el Care es un software automatizado que no cuesta practicamente nada reproducirlo.

**14. Si un cliente te dice "no quiero abono", ¿qué pasa exactamente? ¿Qué SLA tiene y qué no tiene?**
> Tu respuesta: si el cliente no quiere el abono, no pasa nada, se lleva el servidor igual. En ningun momento es obligatorio. Pero el cliente no obtiene monioreo **proactivo** -- avisos antes de que suceda una tragedia -- ni updates. El cliente tiene 30 dias de garantía pero los tickets cuestan 80usd/h y el servicio no es inmediato.

**15. ¿Qué pasa si el cliente se quiere ir a los 14 meses y se quiere llevar los datos? ¿Cuánto paga?**
> Pista: Tabla 7.2 — 66% a 12 meses, 33% a 24. ¿Y si no los quiere?
> Tu respuesta: El cliente tiene 3 opciones. Opción 1: comprar el disco a precio residual. Opción 2: Transfiere los datos a otro disco (propiedad del cliente) y nos devuelve el disco original. Opción 3: no quiere los datos --> ofrecemos un certificado NIST y nos quedamos con el hardware. No nos interesan los números.

---

## Nivel 3 — ¿Podés explicar la técnica sin humo? (Arquitectura)

Si acá tirás humo, el profesor se da cuenta al toque.

**16. Dibujá de memoria las 3 piezas (Central, Agente, Portal) y explicá dónde vive cada una y quién ve qué.**
> Tu respuesta (podés hacer un dibujito a mano):

**17. ¿Qué ve LocalHost Central y qué NUNCA ve? ¿Cómo se lo demostrás a un estudio jurídico paranoico?**
> Tu respuesta:

**18. ¿Qué hace exactamente el "Orquestador" y qué es "la imagen base"? ¿Por qué pasamos de 8hs a 90 min?**
> Tu respuesta:

**19. ¿Qué es el semáforo y por qué es la clave para escalar a 150 clientes sin contratar 5 técnicos más?**
> Tu respuesta:

**20. Explicá WireGuard/Tailscale en una frase sin decir "túnel VPN".**
> Tu respuesta:

**21. ¿Qué pasa si se corta internet en la casa del cliente (Opción A) y qué pasa si se corta en nuestro taller (Opción B)?**
> Tu respuesta:

**22. ¿Qué hace el ticket y por qué no es un WhatsApp suelto?**
> Tu respuesta:

**23. ¿Qué es BYO auditado y cuándo le decís a un cliente "tu equipo no sirve"?**
> Pista: CPU N100, RAM, SMART, <4 años.
> Tu respuesta:

---

## Nivel 4 — Casos borde y objeciones (Las que te van a preguntar y te hacen transpirar)

Si contestás estas fluido, estás listo para exponer.

**24. "Ustedes ven mis fotos igual, no les creo." — ¿Cuáles son tus 4 garantías concretas?**
> Tu respuesta:

**25. "¿Y si pierdo la clave del disco cifrado?" — ¿Qué le contestás? ¿Qué opciones tiene y qué riesgo asume?**
> Tu respuesta:

**26. "Me ofrecen descuento por mis datos, ¿por qué no lo aceptan?" — ¿Por qué lo descartamos y qué ofrecemos en cambio?**
> Pista: Ley 25.326 y telemetría anónima.
> Tu respuesta:

**27. "¿Qué es la telemetría anónima y por qué me dan USD 3-5 de descuento?" — Explicá qué sí y qué nunca recolectan.**
> Tu respuesta:

**28. Se rompe un disco un sábado a la noche. Contá el flujo completo con y sin abono, con y sin seguro, con y sin RAID1.**
> Tu respuesta:

**29. Un cliente te dice: "Quiero pagar el abono por año porque me voy de viaje." — ¿Qué le ofrecés y por qué te conviene a vos también?**
> Tu respuesta:

**30. "¿Y si no tengo lugar en mi casa para el servidor?" — Ya la sabés, pero ¿cuánto paga de más y qué privacidad mantiene?**
> Tu respuesta:

**31. Te toca defender por qué el desarrollo a medida ahora es USD 800 + USD 20/mes y no USD 1500 una vez. ¿Cuál es el argumento de negocio?**
> Tu respuesta:

**32. Si el profesor te dice: "Su Canvas dice 85-90% B2B, pero su Propuesta de Valor dice 'para hogares', ¿no es contradictorio?" — ¿Qué respondés?**
> Tu respuesta:

**33. Explicá LTV y ROI con un ejemplo real del documento (Familia 2TB vs Estudio 4TB).**
> Tu respuesta:

---

## Nivel 5 — Feynman puro (Explicá sin términos técnicos)

Elegí 3 y grabate en audio de 60 segundos. Si tu audio necesita subtítulos, no lo entendiste.

**34. Explicá qué es LocalHost a un nene de 10 años.**
> Tu respuesta:

**35. Explicá qué es el comodato a alguien que solo conoce MercadoPago en cuotas.**
> Tu respuesta:

**36. Explicá por qué "tu nube en tu casa" es más barata a largo plazo que pagar Drive todos los meses, sin usar la palabra "amortización".**
> Tu respuesta:

---

## Autoevaluación rápida

Copiá esta tabla y marcá después de cada ronda:

| Pregunta | 🟢🟡🔴 | ¿Qué me faltó? | ¿Ya lo puedo explicar fluido? |
| :--- | :--- | :--- | :--- |
| 1 | | | |
| 2 | | | |
| ... | | | |
| 33 | | | |

**Regla:** No podés pasar a exponer si tenés más de 3 🔴 o más de 5 🟡 en Nivel 2 y 4. Esos son los que te preguntan.

---

## Respuestas modelo (No mires antes de intentar)

> **No están acá a propósito.** Las respuestas están en `localhost-documento-y-canvas.md` y en el glosario. Si te las doy acá, no hacés Feynman, solo copiás. La gracia es que vos las construyas y después compares.

**Dónde buscar cada nivel:**

- Nivel 1 → §1, §2, §6.3, §7
- Nivel 2 → §2.1, §2.4, §10.2, §10.5, §11.5, §11.10
- Nivel 3 → §6.1, §6.2, §6.4, §7.3, §8.3
- Nivel 4 → §7.4, §7.5, §8, §9, §11 (FAQ completa)

---

> **Próximo paso cuando termines:** Juntate con tu grupo, elijan cada uno 2 preguntas donde se pusieron 🔴 y explíquenselas entre ustedes. Si tu compañero te entiende sin preguntar "¿qué es eso?", aprobaste.

*Archivo generado para LocalHost S.R.L. — Método Feynman — Basado en `consignas-para-definir-la-empresa.pdf` (6 puntos)*
