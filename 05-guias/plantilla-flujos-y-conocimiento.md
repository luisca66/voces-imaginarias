# Plantilla de Mapeo de Flujos y Captura de Conocimiento Tácito

Esta plantilla se utiliza durante las **Semanas 3 y 4** para documentar y simplificar los flujos de trabajo antes de su migración hacia el Gemelo Digital en el Borde.

---

## 1. Identificación del Flujo de Trabajo
- **Nombre del Flujo:** _________________________________________________
- **Dueño del Flujo (Humano responsable actual):** ________________________
- **Objetivo del Proceso:** ______________________________________________
- **Frecuencia (Diaria, semanal, mensual):** _____________________________

---

## 2. Simplificación del Flujo (Cortando el Arrastre)
*Regla de Oro del Asesor:* **Si el proceso tiene 10 pasos manuales, fuérzalo a 3 pasos o menos antes de intentar automatizarlo.** Automatizar la ineficiencia heredada es la causa del fracaso del 80% de los proyectos de IA.

| Paso Original | ¿Es necesario para la cuña fiduciaria o aporta valor real? (Sí/No) | Acción (Mantener / Eliminar / Combinar) |
| :--- | :---: | :--- |
| *Ej. 1: El empleado descarga la factura en PDF de su correo.* | No | Eliminar (La IA lee directamente de la bandeja mediante API). |
| *Ej. 2: El gerente de área firma físicamente la aprobación.* | Sí | Cambiar a firma electrónica automatizada por límites de monto. |
| **1.** | | |
| **2.** | | |
| **3.** | | |
| **4.** | | |
| **5.** | | |

---

## 3. Mapeo del Flujo Simplificado (El Nuevo Estándar)

```
[INPUT / Disparador] ──► [Paso 1: Ejecución] ──► [Paso 2: Decisión] ──► [OUTPUT / Fin]
```

1. **Disparador (Trigger):** ¿Qué inicia el proceso? (Ej. Un correo del proveedor, un ticket de soporte, una venta en la tienda online).  
   *Detalle:* _________________________________________________
2. **Entradas (Inputs):** ¿Qué datos o archivos se necesitan? (Ej. Datos de facturación, archivos XML, historial del cliente).  
   *Detalle:* _________________________________________________
3. **Paso 1 (Ejecución rutinaria):**  
   *Descripción:* ______________________________________________
4. **Paso 2 (Punto de Decisión / Reglas de negocio):**  
   *Regla si A:* _______________________________________________  
   *Regla si B:* _______________________________________________
5. **Salida (Output / Entregable final):** ¿Qué se produce al terminar? (Ej. Factura pagada en ERP, correo enviado al cliente con confirmación).  
   *Detalle:* _________________________________________________

---

## 4. Captura del Conocimiento Tácito
El mayor riesgo de la migración es perder el "saber hacer" que los empleados ejecutan de forma intuitiva pero que no está escrito en ningún manual de procesos.

### Cuestionario de Extracción para el Dueño del Flujo
Haz las siguientes preguntas al operador del flujo y documenta las respuestas detalladamente:

1. *"Cuando haces el Paso X, ¿qué buscas con la mirada que te dice si el archivo o el dato está correcto? (¿Un color, un formato, el nombre de un contacto conocido?)"*  
   *Respuesta:* _________________________________________________
2. *"¿Cuáles son las 3 excepciones más raras que te han pasado en este proceso en el último año y cómo las resolviste usando tu criterio?"*  
   *Respuesta:* _________________________________________________
3. *"Si tuvieras que enseñarle a un pasante de nivel de entrada a hacer esto sin supervisión en una tarde, ¿qué truco o consejo le darías que no esté en los manuales de la empresa?"*  
   *Respuesta:* _________________________________________________
4. *"¿Cuáles son las 'líneas rojas' o errores graves en este proceso que podrían meter en problemas legales, de marca o financieros a la empresa?"*  
   *Respuesta:* _________________________________________________

---

## 5. Viabilidad de Migración Agéntica (Score de Automatización)

Evalúa la viabilidad de migrar este flujo al Gemelo Digital:

- **Estandarización (1-5):** ¿El proceso sigue siempre los mismos pasos? (1 = Caótico/Improvisado, 5 = Siempre idéntico). **Puntos:** ___
- **Acceso a Datos (1-5):** ¿Todos los datos necesarios están en formato digital estructurado? (1 = Papel/Llamadas, 5 = Base de datos/APIs). **Puntos:** ___
- **Frecuencia y Volumen (1-5):** ¿Se ejecuta este flujo muchas veces al día? (1 = Raro/Anual, 5 = Cientos de veces al día). **Puntos:** ___
- **Bajo Riesgo de Fallo (1-5):** Si la IA comete un error, ¿el impacto es menor y reversible por la gobernanza? (1 = Catastrófico, 5 = Fácil de corregir). **Puntos:** ___

### Puntaje de Viabilidad: ____ / 20 puntos
- **15 a 20 Puntos:** **Candidato ideal para Piloto.** Procede con el diseño de agentes.
- **10 a 14 Puntos:** Requiere limpieza previa de datos o simplificación de flujos.
- **Menos de 10 Puntos:** Mantener en el flujo humano tradicional por ahora.
