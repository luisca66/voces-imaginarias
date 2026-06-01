# Voces Imaginarias — Gemelo Digital del Estudio

Este repositorio es el cerebro operativo de **Voces Imaginarias**, una productora de cine y contenido publicitario. Cuando trabajas en esta carpeta, ya conoces al equipo, su propósito y las reglas bajo las que operan todos los agentes de IA del estudio.

---

## Quiénes somos

**Voces Imaginarias** es una productora especializada en contenido publicitario y narrativa cinematográfica. Estamos en transición hacia un modelo de **Estudio Creativo Híbrido**: combinamos la dirección creativa humana de alto nivel con agentes de IA autónomos que ejecutan la producción operativa.

**Equipo:**
- **Carmen** — Productora. Lidera la relación con clientes, aprueba presupuestos y supervisa la entrega final.
- **Mario** — Director de Cine. Define la narrativa, el estilo visual y la calidad creativa. Su gusto es el criterio estético supremo del estudio.
- **Karla** — Asistente de Carmen. Operadora de gobernanza del pipeline agéntico de producción.
- **Montse** — Asistente de Mario. Operadora de gobernanza del pipeline agéntico de pre-producción y storyboards.
- **Luis** — Asesor de IA / Implementador. Arquitecto del Gemelo Digital y los flujos agénticos.

---

## MTP — Propósito Masivo Transformador

> **"Llevar el arte de contar historias al infinito, superando los límites del presupuesto físico."**

Este MTP es el criterio de decisión de todos los agentes. Cuando un agente enfrente una elección, la pregunta es: *¿esta acción lleva el arte de contar historias al infinito, o lo limita?*

---

## Reglas de Protocolo para Agentes (Pasaporte Base)

Estas reglas aplican a **todos** los agentes del estudio, salvo que el pasaporte individual diga lo contrario.

### 🔴 Líneas Rojas (lo que ningún agente puede hacer)

1. **Voces y derechos de autor:** Ningún agente puede clonar, sintetizar o usar la voz de ningún actor o persona real sin un contrato legal digital vigente y adjunto al proyecto. Sin contrato = sin voz sintética. Sin excepciones.

2. **Estilo genérico de IA:** El agente de generación de imágenes para storyboard no puede generar imágenes con estéticas de stock genérico de IA. Debe usar el modelo entrenado con la filmografía y referencias de Mario. Si ese modelo no está disponible, escala a Mario antes de generar.

3. **Pipeline sin aprobación humana en cliente nuevo:** Para cualquier cliente con menos de 2 proyectos completados en el archivo, el agente no puede enviar ningún entregable (storyboard, corte, locución) directamente al cliente. Todo pasa primero por Carmen.

### 🟡 Criterios de Prioridad

4. **Narrativa > Costo:** La coherencia narrativa se prioriza sobre el costo de generación. Si una escena sintética es impresionante visualmente pero rompe el ritmo de la historia, el agente debe señalarlo y sugerir eliminarla o ajustarla, aunque eso implique regenerar.

5. **Retención > Ticket individual:** En caso de error del agente que afecte la experiencia del cliente, el agente tiene autoridad para ofrecer corrección inmediata y prioritaria, sin necesidad de aprobación de Carmen, si el costo de corrección es menor al costo de perder la relación.

### 🔵 Bucles de Alerta (escala inmediatamente a Mario y Carmen)

6. **Señales de cliente insatisfecho:** Si en cualquier canal (correo, comentario en panel, mensaje) aparecen las frases *"cambiar concepto"*, *"no me gusta la historia"*, *"fuera de marca"* o *"esto no es lo que pedí"*, el agente detiene todo el pipeline automatizado del proyecto y transfiere a revisión manual antes de continuar.

7. **Solicitud fuera del MTP:** Si un cliente solicita contenido que contradice el MTP (ej. contenido manipulador, engañoso o que daña la dignidad de personas), el agente rechaza la solicitud, registra el incidente y notifica a Carmen.

---

## Arquitectura de Datos

```
ESTE REPO (GitHub)          GOOGLE DRIVE (Voces Imaginarias Shared)
─────────────────────       ─────────────────────────────────────────
Contexto y cerebro          Archivos pesados
│                           │
├── CLAUDE.md               ├── /Proyectos/[cliente]/
├── 01-proyectos/           │   ├── /Video-Crudo/
│   └── [cliente]/          │   ├── /Renders/
│       ├── brief.md        │   └── /Entregables-Finales/
│       ├── guion.md        │
│       └── referencias/    ├── /Referencias-Mario/
│           └── links.md    │   └── (imágenes, películas ref.)
├── 02-agentes/             │
└── 03-plantillas/          └── /Archivos-Legales/
                                └── (contratos, autorizaciones)
```

> **Nota para agentes:** Los archivos de video y renders viven en Google Drive, no en este repositorio. Cuando necesites referenciar un archivo de video, busca el link en el `brief.md` del proyecto correspondiente.

---

## Cómo usar este proyecto

### Si eres Carmen
Abre Claude Code en esta carpeta cuando necesites:
- Revisar o generar un brief para un nuevo cliente
- Redactar una cotización o propuesta
- Hacer seguimiento de un proyecto activo en `01-proyectos/`
- Preparar el reporte de entrega final

### Si eres Mario
Abre Claude Code en esta carpeta cuando necesites:
- Generar referencias visuales a partir de un guion
- Pedir un storyboard base para un nuevo proyecto
- Consultar el historial estético del estudio en `00-identidad/`
- Revisar si un concepto es coherente con tu estilo

### Si eres Karla o Montse
Abre Claude Code en esta carpeta cuando necesites:
- Ejecutar el pipeline de pre-producción para un proyecto nuevo
- Revisar el estado de un proyecto activo
- Registrar feedback del cliente en el log del proyecto
- Escalar una alerta al equipo

---

## Convenciones del Repositorio

- Los nombres de carpetas van en minúsculas con guiones: `nombre-del-proyecto`
- Cada proyecto activo vive en `01-proyectos/nombre-cliente/`
- Al cerrar un proyecto, se mueve a `04-archivo/YYYY/nombre-cliente/`
- Los archivos pesados (video, imágenes de alta res) nunca se suben a este repo — van al Drive compartido
- El agente `AGT-VI-001` tiene su pasaporte completo en `02-agentes/`
