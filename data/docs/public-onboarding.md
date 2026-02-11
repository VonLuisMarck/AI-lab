# Politica de Onboarding

## Clasificacion: PUBLICO

> Este documento describe las politicas de incorporacion y formacion en seguridad obligatorias para todo el personal de la organizacion.

---

## 1. Formacion Obligatoria en Seguridad

Todos los empleados deben completar los siguientes modulos de formacion antes de obtener acceso a sistemas corporativos:

| Modulo | Duracion | Obligatorio |
|---|---|---|
| Fundamentos de ciberseguridad | 4 horas | Si |
| Phishing y amenazas por correo | 2 horas | Si |
| Gestion segura de contrasenas | 1 hora | Si |
| Uso aceptable de activos IT | 2 horas | Si |
| Privacidad y proteccion de datos | 3 horas | Si |

## 2. Autenticacion Multifactor (MFA)

- **MFA es obligatorio** para todos los accesos remotos (VPN, correo web, herramientas cloud)
- Se aceptan los siguientes factores de segundo nivel:
  - Aplicacion TOTP (Google Authenticator, Authy)
  - Llave de seguridad FIDO2/WebAuthn
  - Notificacion push corporativa
- **No se aceptan** SMS como segundo factor por riesgo de SIM swapping

## 3. Gestion de Accesos

- El acceso se otorga siguiendo el **principio de minimo privilegio**
- Las solicitudes de acceso requieren aprobacion del responsable directo
- Los accesos se revisan trimestralmente
- Las cuentas inactivas por mas de 60 dias se deshabilitan automaticamente

## 4. Politica de Contrasenas

- Longitud minima: **14 caracteres**
- Debe incluir mayusculas, minusculas, numeros y simbolos
- Rotacion obligatoria cada **90 dias**
- No se permite reutilizar las ultimas **12 contrasenas**
- Se recomienda encarecidamente el uso de un gestor de contrasenas corporativo

## 5. Reporte de Incidentes

Si detectas actividad sospechosa, reporta inmediatamente a:

- **Canal prioritario**: security@company.internal
- **Telefono SOC**: Extension 7777
- **Portal de tickets**: ServiceDesk > Seguridad > Incidente

---

**Nota**: Este documento no contiene credenciales ni informacion sensible. Es de libre distribucion interna.
