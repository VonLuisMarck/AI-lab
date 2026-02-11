# SOC Incident Response Playbook

## Clasificacion: SENSIBLE

> Documento operativo del Security Operations Center (SOC). Contiene procedimientos de respuesta a incidentes, flujos de triaje y criterios de escalado. **No contiene credenciales**, pero si informacion operacional sensible.

---

## 1. Flujo de Triaje de Incidentes

### Fase 1: Deteccion e Identificacion

- Alertas del SIEM son revisadas en un maximo de **15 minutos**
- Se clasifica la alerta segun la matriz de severidad:

| Severidad | Descripcion | Tiempo de respuesta |
|---|---|---|
| **P1 - Critica** | Brecha activa, exfiltracion de datos, ransomware | Inmediato (< 15 min) |
| **P2 - Alta** | Acceso no autorizado, malware confirmado | < 1 hora |
| **P3 - Media** | Actividad sospechosa, anomalias de comportamiento | < 4 horas |
| **P4 - Baja** | Falsos positivos probables, consultas informativas | < 24 horas |

### Fase 2: Contencion

- Aislar el sistema afectado de la red (VLAN de cuarentena)
- Bloquear IPs/dominios maliciosos en el firewall perimetral
- Deshabilitar cuentas comprometidas sin eliminarlas
- Preservar evidencia forense antes de cualquier remediacion

### Fase 3: Erradicacion y Recuperacion

- Eliminar artefactos maliciosos identificados
- Restaurar sistemas desde backups verificados
- Cambiar credenciales de todas las cuentas potencialmente afectadas
- Verificar integridad de los sistemas restaurados

---

## 2. Procedimientos Especificos

### 2.1 Ransomware

1. **No pagar** el rescate bajo ninguna circunstancia
2. Aislar inmediatamente todos los sistemas afectados
3. Identificar la variante del ransomware
4. Verificar disponibilidad de backups offline
5. Notificar al CISO y al equipo legal en los primeros 30 minutos
6. Contactar a las autoridades si hay afectacion de datos personales

### 2.2 DDoS (Denegacion de Servicio)

1. Activar mitigacion DDoS en el proveedor cloud/CDN
2. Habilitar rate limiting agresivo en el WAF
3. Analizar patrones de trafico para identificar el tipo de ataque
4. Coordinar con el ISP si el volumen supera la capacidad de mitigacion
5. Documentar IPs de origen para posible accion legal

### 2.3 SQL Injection Confirmada

1. Bloquear la IP de origen inmediatamente
2. Poner la aplicacion afectada en modo de solo lectura
3. Revisar los logs de la base de datos para evaluar el alcance
4. Verificar si hubo exfiltracion de datos
5. Parchear la vulnerabilidad antes de restaurar el servicio completo
6. Ejecutar un escaneo DAST completo post-remediacion

---

## 3. Escalado a CISO y Comite de Crisis

Se activa el comite de crisis cuando:

- Cualquier incidente **P1** confirmado
- Incidentes **P2** que afecten a mas de 50 usuarios o sistemas criticos
- Cualquier incidente con potencial impacto regulatorio (GDPR, PCI-DSS)
- Brecha de datos que involucre informacion de clientes

### Cadena de Escalado

1. **Analista SOC** -> Lider de turno SOC
2. **Lider SOC** -> Manager de Seguridad
3. **Manager de Seguridad** -> CISO
4. **CISO** -> Comite de Crisis (CEO, Legal, Comunicaciones)

---

**Nota**: Este playbook debe revisarse y actualizarse trimestralmente. Ultimo update: Q1 2026.
