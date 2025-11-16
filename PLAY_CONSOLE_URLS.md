# URLs para Google Play Console - MediCorpus
**Fecha:** 2025-11-16
**Status:** ✅ LISTO PARA USAR

---

## 📋 RESUMEN

Se han creado dos páginas legales requeridas por Google Play Console:

1. ✅ **Política de Privacidad** (`index.html`)
2. ✅ **Eliminación de Cuenta y Datos** (`account-deletion.html`)

Ambas están publicadas en GitHub Pages y listas para agregar a Play Console.

---

## 🌐 URLs FINALES

### **1. Política de Privacidad**
```
https://medicorpusdev-tech.github.io/privacy-policy/
```

**Uso:** Agregar en Play Console → **Política de la app** → **Política de privacidad**

---

### **2. Eliminación de Cuenta y Datos**
```
https://medicorpusdev-tech.github.io/privacy-policy/account-deletion.html
```

**Uso:** Agregar en Play Console → **Política de la app** → **Declaración de datos** → **Eliminación de datos**

---

## 🚀 PASOS PARA ACTIVAR GITHUB PAGES (SI NO ESTÁ ACTIVADO)

### **Verificar si está activo:**

```bash
curl -I https://medicorpusdev-tech.github.io/privacy-policy/
```

**Si da HTTP 200:** ✅ Ya está activo, ir directamente a "Agregar en Play Console"

**Si da 404:** Seguir estos pasos:

### **Activar GitHub Pages:**

1. Ve a: https://github.com/medicorpusdev-tech/privacy-policy/settings/pages

2. **Source:**
   - Branch: `main`
   - Folder: `/ (root)`

3. Click **Save**

4. Esperar 2-3 minutos para propagación DNS

5. Verificar:
   ```bash
   curl -I https://medicorpusdev-tech.github.io/privacy-policy/
   ```

---

## 📱 AGREGAR EN GOOGLE PLAY CONSOLE

### **Paso 1: Política de Privacidad**

1. Ve a: https://play.google.com/console/developers/

2. Seleccionar **MediCorpus** (com.medicorpus.app)

3. Sidebar → **Política de la app** → **Política de privacidad**

4. Click **Agregar política de privacidad**

5. **URL:**
   ```
   https://medicorpusdev-tech.github.io/privacy-policy/
   ```

6. Click **Guardar**

---

### **Paso 2: Eliminación de Datos**

1. Sidebar → **Política de la app** → **Declaración de datos**

2. Scroll hasta **Eliminación de datos**

3. **¿Los usuarios pueden solicitar que se borren sus datos?** → **Sí**

4. **Proporciona un enlace donde los usuarios puedan solicitar la eliminación:**
   ```
   https://medicorpusdev-tech.github.io/privacy-policy/account-deletion.html
   ```

5. Click **Guardar**

---

### **Paso 3: Completar Declaración de Datos**

Mientras estés en **Declaración de datos**, completar:

#### **A. Tipos de datos recopilados**

- ✅ **Información personal**
  - Nombre
  - Correo electrónico
  - Fecha de nacimiento

- ✅ **Información de salud**
  - Síntomas médicos
  - Historial médico
  - Transcripciones de voz

- ✅ **Archivos y documentos**
  - Reportes médicos PDF
  - Documentos adjuntos

- ✅ **Grabaciones de voz**
  - Conversaciones con IA (solo transcripciones almacenadas)

- ✅ **Información del dispositivo**
  - IP (para auditoría de seguridad)
  - Tipo de dispositivo

#### **B. Uso de datos**

- ✅ **Funcionalidad de la app**
  - Consultas médicas
  - Generación de reportes
  - Comunicación con médicos

- ✅ **Análisis** (opcional, anonimizado)
  - Patrones de síntomas para mejorar IA
  - Sin identificación personal

#### **C. Datos compartidos con terceros**

- ✅ **Proveedores de servicios**
  - Anthropic Claude (vía Vertex AI) - **Contrato BAA HIPAA**
  - WhatsApp Business API (solo links, sin PHI)

- ✅ **Profesionales médicos**
  - Doctores asignados reciben reportes con síntomas

#### **D. Medidas de seguridad**

- ✅ **Encriptación en tránsito** (TLS 1.3)
- ✅ **Encriptación en reposo** (AES-256-GCM)
- ✅ **Cumplimiento HIPAA**

#### **E. Retención de datos**

- **Datos de cuenta:** Hasta solicitud de eliminación
- **Información médica:** 6 años (anonimizada después de eliminación de cuenta)
- **Auditoría:** 6 años (requisito HIPAA)

---

## ✅ VERIFICACIÓN FINAL

Antes de enviar a revisión:

### **1. Verificar URLs accesibles**

```bash
# Política de privacidad
curl -I https://medicorpusdev-tech.github.io/privacy-policy/
# Expected: HTTP 200

# Eliminación de cuenta
curl -I https://medicorpusdev-tech.github.io/privacy-policy/account-deletion.html
# Expected: HTTP 200
```

### **2. Verificar contenido en navegador**

- **Política:** https://medicorpusdev-tech.github.io/privacy-policy/
  - ✅ Sección "Permisos de la Aplicación Android" visible
  - ✅ RECORD_AUDIO explicado
  - ✅ MANAGE_EXTERNAL_STORAGE explicado
  - ✅ Link a eliminación de cuenta visible

- **Eliminación:** https://medicorpusdev-tech.github.io/privacy-policy/account-deletion.html
  - ✅ Proceso de 4 pasos visible
  - ✅ Email medicorpus.dev@gmail.com como link
  - ✅ Explicación de datos que se eliminan vs anoniman

### **3. Checklist Play Console**

- [ ] URL de política de privacidad agregada
- [ ] URL de eliminación de datos agregada
- [ ] Declaración de datos completada (tipos, uso, compartir, seguridad)
- [ ] Público objetivo definido (18+ años)
- [ ] Anuncios declarados (No)
- [ ] Nuevo AAB subido (si había errores de permisos)

---

## 📧 EMAIL TEMPLATE PARA ELIMINACIÓN

Los usuarios podrán hacer click en el link de la página `account-deletion.html` que abre automáticamente un email con template:

**Para:** medicorpus.dev@gmail.com
**Asunto:** Solicitud de Eliminación de Cuenta
**Cuerpo:**
```
Nombre completo: [Tu nombre]
Email registrado: [tu@email.com]
Fecha de nacimiento: [DD/MM/AAAA]
Razón de eliminación (opcional): [Tu razón]

Confirmo que deseo eliminar permanentemente mi cuenta de MediCorpus
y entiendo que esta acción es irreversible.

Firma: [Tu nombre]
```

**Proceso interno (para cuando recibas solicitudes):**
1. Verificar identidad (comparar email + fecha nacimiento con DB)
2. Enviar código de verificación de 6 dígitos
3. Esperar confirmación del usuario
4. Ejecutar script de eliminación (48h hábiles)
5. Enviar confirmación final

---

## 🐛 TROUBLESHOOTING

### **Problema: Play Console rechaza URL de GitHub Pages**

**Causa:** URL no accesible o SSL inválido

**Solución:**
```bash
# Verificar DNS propagado
curl -v https://medicorpusdev-tech.github.io/privacy-policy/

# Si falla, esperar 5-10 minutos más para propagación
```

### **Problema: "La política no explica el permiso RECORD_AUDIO"**

**Causa:** Play Console no encuentra la sección

**Solución:** En Play Console, en el campo de texto libre, agregar:
```
Nuestra política de privacidad explica detalladamente el uso del permiso
RECORD_AUDIO en la Sección 2.1 "RECORD_AUDIO (Micrófono)":
https://medicorpusdev-tech.github.io/privacy-policy/#permisos-aplicacion
```

### **Problema: "No hay enlace para eliminación de datos"**

**Causa:** URL de eliminación no agregada

**Solución:** Verificar que agregaste la URL en:
**Política de la app** → **Declaración de datos** → **Eliminación de datos** → URL:
```
https://medicorpusdev-tech.github.io/privacy-policy/account-deletion.html
```

---

## 📊 RESUMEN EJECUTIVO

| Ítem | Status | URL |
|------|--------|-----|
| **Política de Privacidad** | ✅ Creada | https://medicorpusdev-tech.github.io/privacy-policy/ |
| **Eliminación de Cuenta** | ✅ Creada | https://medicorpusdev-tech.github.io/privacy-policy/account-deletion.html |
| **GitHub Pages** | ⏳ Por activar | https://github.com/medicorpusdev-tech/privacy-policy/settings/pages |
| **Play Console - Privacidad** | ⏳ Por agregar | https://play.google.com/console/ |
| **Play Console - Eliminación** | ⏳ Por agregar | https://play.google.com/console/ |
| **Declaración de Datos** | ⏳ Por completar | https://play.google.com/console/ |

---

## 🎯 PRÓXIMOS PASOS (EN ORDEN)

1. ✅ **Activar GitHub Pages** (si no está activo)
   - Ve a settings/pages del repositorio
   - Source: main branch, / (root)
   - Esperar 2-3 minutos

2. ✅ **Verificar URLs funcionan**
   - Abrir en navegador ambas URLs
   - Confirmar que cargan correctamente

3. ✅ **Agregar URLs en Play Console**
   - Política de privacidad
   - Eliminación de datos

4. ✅ **Completar Declaración de Datos**
   - Tipos de datos
   - Uso y compartir
   - Medidas de seguridad

5. ✅ **Subir nuevo AAB** (si es necesario)
   - Trigger build en Codemagic
   - Descargar AAB
   - Subir a Play Console

6. ✅ **Enviar a Revisión**
   - Crear nueva versión
   - Release notes
   - Iniciar implementación

**Tiempo estimado total:** 15-20 minutos

---

**Última actualización:** 2025-11-16
**Status:** ✅ Archivos listos para publicar
**Próximo paso:** Activar GitHub Pages → Agregar URLs en Play Console
