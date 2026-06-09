# Pasaporte del Agente: Especificación de Seguridad y Límites

Cada agente de IA que opere dentro del **Gemelo Digital** debe contar con su propio pasaporte activo y documentado. Ningún agente puede desplegarse en producción sin este registro.

---

## 1. Identificación del Agente
- **ID del Agente:** `AGT-________________`
- **Nombre Clave:** _________________________________________________
- **Versión de Software / Modelo Base:** _______________________________
- **Objetivo Único (Misión):** _________________________________________
- **Rol en el Stack (Sensado, Interpretación, Decisión, Orquestación):** _________________

---

## 2. Límites y Políticas de API (Policy-Controlled APIs)
El agente interactúa con el mundo mediante APIs controladas. Define los alcances exactos:

- **APIs de Lectura Permitidas:**
  - `[ ]` Directorio de correos (Bandeja específica: `soporte@...`)
  - `[ ]` Base de datos de productos (Solo SKU y Precios)
  - `[ ]` Historial de facturas de clientes
  - `[ ]` Otras: _________________________________________________
- **APIs de Escritura Permitidas:**
  - `[ ]` Enviar correos (Solo respuestas plantilla)
  - `[ ]` Modificar base de datos (Requiere confirmación de stock)
  - `[ ]` Otras: _________________________________________________
- **Líneas Rojas (Endpoints Prohibidos):**
  - El agente **no tiene permitido** acceder a:
    1. Datos de pasarelas de pago (Stripe, Paypal, etc.) directos.
    2. Modificación de cuentas bancarias de proveedores.
    3. Información de nómina de los empleados.

---

## 3. Seguridad de Datos por Objeto (Data Object Security)
- **Clasificación de Datos Permitidos:**
  - `[x]` Públicos (Precios, catálogo)
  - `[ ]` Internos no confidenciales (Stock de inventario, minutas)
  - `[ ]` Confidenciales (Datos personales de clientes - encriptar o enmascarar)
- **Política de Enmascaramiento:**
  - El agente debe aplicar filtros regex para ocultar:
    - Tarjetas de crédito/débito: `[0-9]{16}`
    - Contraseñas o tokens de acceso en los logs.

---

## 4. Marco de Responsabilidad y Presupuesto (Liability & Budget)
- **Costo Máximo por API Call (Tokens):** $_________ USD.
- **Presupuesto Máximo Diario:** $_________ USD. (Si se excede, el agente se suspende y envía alerta).
- **Límite de Transacción Financiera:**
  - El agente puede autorizar un reembolso o descuento de máximo: $_________ USD.
  - Montos superiores **deben** enviarse a la Cola de Revisión Humana.

---

## 5. Protocolo de Excepciones y Rollback
- **Criterios de Fallo (Cuándo detener al agente):**
  - Confianza de respuesta menor a: ______%
  - Detección de lenguaje ofensivo o manipulación del prompt (Prompt Injection) por parte del usuario.
  - Error HTTP repetido más de 3 veces.
- **Acción ante Fallo:**
  - Detener ejecución, revertir transacciones en base de datos (Rollback granular) y crear ticket con ID en:  
    `[ ]` Cola de revisión humana: `http://...`
    `[ ]` Alerta por Slack / Whatsapp al Asesor / Dueño de flujo.

---

## 6. Firmas de Aprobación
- **Firma del Diseñador (Asesor/Builder):** ___________________________
- **Firma del Dueño Fiduciario (CEO/Fundador PyME):** _________________
- **Fecha de Activación:** ____/____/______
