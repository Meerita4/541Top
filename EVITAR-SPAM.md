# ⚠️ SOLUCIÓN: Los emails del formulario llegan a SPAM

## Problema
Los correos enviados desde Formspree pueden llegar a la carpeta de spam porque no están autenticados desde tu dominio.

## Soluciones Implementadas en el Código

### 1. ✅ Campo `_subject` personalizado
```html
<input type="hidden" name="_subject" value="Nuevo mensaje de contacto - 541TOP Sailcoach" />
```
Esto hace que el asunto del email sea más profesional y reconocible.

### 2. ✅ Campo de email correcto
Cambiado de `name="_replyto"` a `name="email"` para que Formspree lo procese correctamente.

### 3. ✅ Campo de asunto visible
Agregado un selector de asunto para categorizar mejor los mensajes.

### 4. ✅ Honeypot mejorado
El campo anti-spam tiene atributos adicionales (`tabindex="-1"` y `autocomplete="off"`).

---

## 🔧 Configuración REQUERIDA en Formspree

### Paso 1: Configurar el Email Sender
1. Ve a tu formulario en Formspree: https://formspree.io/forms
2. Click en el formulario activo (mblnqarv)
3. Settings → **Email Settings**
4. Configura:
   - **From Name**: `541TOP Sailcoach`
   - **From Email**: Usa el email que verificaste en Formspree
   - **Reply To**: Dejalo en automático para que use el email del usuario

### Paso 2: Verificar tu Dominio (IMPORTANTE)
Si tienes un dominio propio (ej: 541top.com):
1. Settings → **Domain Verification**
2. Verifica tu dominio siguiendo las instrucciones
3. Esto mejora significativamente la deliverability

### Paso 3: Activar Protección Anti-Spam
1. Settings → **Spam Protection**
2. Activa **reCAPTCHA v3** (invisible para usuarios)
3. O activa **hCaptcha** si prefieres

### Paso 4: Configurar Respuesta Automática
1. Settings → **Autoresponder**
2. Activa el autoresponder
3. Personaliza el mensaje:
```
Asunto: Hemos recibido tu mensaje - 541TOP Sailcoach

Hola,

¡Gracias por contactar con 541TOP Sailcoach!

Hemos recibido tu mensaje y te responderemos en las próximas 24 horas.

Mientras tanto, puedes contactarnos por WhatsApp: +34 616 011 752

¡Nos vemos en el agua!

Equipo 541TOP Sailcoach
```

---

## 📧 Configuración en tu Cliente de Correo

### Gmail
1. **Añadir a contactos**:
   - Cuando recibas el primer email de Formspree, haz click en el remitente
   - Click en "Agregar a contactos"

2. **Crear filtro**:
   - Configuración (⚙️) → Ver todos los ajustes → Filtros y direcciones bloqueadas
   - Crear un filtro nuevo
   - **De**: `formspree.io`
   - Crear filtro → ✅ "Nunca enviar a spam"
   - ✅ "Marcar como importante"
   - ✅ "Aplicar la etiqueta" → Nueva etiqueta: `541TOP - Contactos`

3. **Marcar como no spam manualmente**:
   - Si ya hay emails en spam, selecciónalos
   - Click en "No es spam"

### Outlook / Hotmail
1. **Añadir remitente seguro**:
   - Configuración → Ver toda la configuración
   - Correo → Correo no deseado
   - Remitentes seguros → Agregar
   - Añade: `formspree.io` y `noreply@formspree.io`

2. **Crear regla**:
   - Configuración → Reglas
   - Nueva regla
   - Condición: "El remitente contiene" → `formspree.io`
   - Acción: "Mover a" → Bandeja de entrada
   - ✅ "Marcar como importante"

---

## 🚀 Solución Avanzada: Dominio Propio

Si tienes un dominio propio, la mejor solución es:

### Opción A: Usar Resend (Recomendado)
Resend es gratuito hasta 3,000 emails/mes y tiene mejor deliverability:

1. Regístrate en https://resend.com
2. Verifica tu dominio
3. Configura registros DNS (SPF, DKIM)
4. Crea una API key

### Opción B: Configurar SPF para Formspree
Añade este registro TXT en tu DNS:
```
v=spf1 include:formspree.io include:_spf.google.com ~all
```

### Opción C: Usar Email Propio
Si tienes email profesional (ej: contacto@541top.com):
1. En Formspree Settings → Email Settings
2. Usa tu email verificado del dominio
3. Esto hará que los emails vengan "de" tu dominio

---

## ✅ Checklist Final

- [ ] Configurar "From Name" en Formspree como "541TOP Sailcoach"
- [ ] Verificar dominio en Formspree (si aplica)
- [ ] Activar reCAPTCHA v3 o hCaptcha
- [ ] Configurar autoresponder
- [ ] Añadir formspree.io a contactos en Gmail/Outlook
- [ ] Crear filtro "Nunca enviar a spam"
- [ ] Marcar los emails actuales en spam como "No es spam"
- [ ] (Opcional) Configurar dominio propio con SPF/DKIM

---

## 🔍 Debugging

Si sigues teniendo problemas:

1. **Verifica que lleguen emails**:
   - Haz una prueba desde el formulario
   - Revisa en Formspree → Submissions si se recibió

2. **Revisa headers del email**:
   - En Gmail: Abrir email → ⋮ → Mostrar original
   - Busca: `SPF`, `DKIM`, `DMARC`
   - Debería decir `PASS` o al menos `NEUTRAL`

3. **Contacta a Formspree**:
   - Si todo está configurado y aún hay problemas
   - support@formspree.io

---

## 💡 Tip Extra

Mientras configuras todo, **reenvia los emails de Formspree** a un servicio que procese mejor:
- Crea un email de Gmail específico para formularios
- En ese Gmail, configura reenvío automático a tu email principal
- El reenvío desde Gmail tiene mejor deliverability
