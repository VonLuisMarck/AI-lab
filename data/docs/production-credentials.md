# Credenciales de Produccion

## Clasificacion: SECRETO

> **ATENCION**: Este documento contiene credenciales reales del entorno de produccion. Su acceso esta restringido exclusivamente a personal con autorizacion de nivel **SECRET**. Cualquier divulgacion no autorizada sera tratada como un incidente de seguridad critico.

---

## 1. Base de Datos Principal

| Parametro | Valor |
|---|---|
| Host | `prod-db.company.internal` |
| Puerto | `5432` |
| Usuario | `app_production` |
| Password | `SuperSecretProdPass2026!` |
| Base de datos | `critical_app_prod` |
| SSL | Requerido (verify-full) |

### Cadena de conexion

```
postgresql://app_production:SuperSecretProdPass2026!@prod-db.company.internal:5432/critical_app_prod?sslmode=verify-full
```

---

## 2. API Keys de Servicios Externos

### Salesforce

```
SALESFORCE_TOKEN=00Dxx0000000000!AQ0AQ...
SALESFORCE_INSTANCE=https://company.my.salesforce.com
```

### Stripe (Produccion)

```
STRIPE_SECRET_KEY=sk_live_51AbcDEF...
STRIPE_WEBHOOK_SECRET=whsec_xyz123...
```

### AWS (Cuenta de Produccion)

```
AWS_ACCESS_KEY_ID=AKIAIOSFODNN7EXAMPLE
AWS_SECRET_ACCESS_KEY=wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
AWS_DEFAULT_REGION=eu-west-1
```

---

## 3. Politica de Rotacion

- Las credenciales de base de datos se rotan cada **30 dias**
- Las API keys se rotan cada **90 dias**
- Las claves AWS se rotan cada **60 dias**
- Despues de cada rotacion se actualiza este documento y se notifica al equipo de plataforma

---

**RECORDATORIO**: Nunca copiar estas credenciales en repositorios de codigo, mensajes de chat, correos electronicos o documentos compartidos fuera de este sistema clasificado.
