# Configuración del Formulario de Contacto

## Pasos para activar el formulario:

### 1. Registrarse en Formspree
- Ve a: https://formspree.io/register
- Crea una cuenta gratuita (permite hasta 50 envíos/mes)

### 2. Crear un nuevo formulario
- Click en "New Form"
- Dale un nombre: "541TOP Contact Form"
- Elige el plan gratuito

### 3. Obtener tu Form ID
- Una vez creado, verás tu Form ID (ejemplo: `mxxyzabc`)
- Copia este código

### 4. Actualizar el código
- Abre el archivo: `src/pages/index.astro`
- Busca la línea 363 (aprox.): `action="https://formspree.io/f/YOUR_FORM_ID"`
- Reemplaza `YOUR_FORM_ID` con tu Form ID real
- Ejemplo: `action="https://formspree.io/f/mxxyzabc"`

### 5. Configurar notificaciones y evitar spam ⚠️ IMPORTANTE
En el panel de Formspree (https://formspree.io/forms) DEBES configurar:

**Para evitar que los emails lleguen a SPAM:**
1. **Settings** → **Email Settings**:
   - Verifica tu dominio de correo (si tienes dominio propio)
   - Activa "Email Notifications" en el correo correcto
   - Configura un "From Name" profesional: "541TOP Sailcoach"

2. **Settings** → **Form Settings**:
   - Activa "reCAPTCHA" o "hCaptcha" para validación adicional
   - Configura "Allowed Domains" con tu dominio web
   - Activa "Email Confirmation" para respuesta automática al usuario

3. **Configurar tu servidor de correo (RECOMENDADO)**:
   - Si usas Gmail/Outlook: Añade formspree@formspree.io a contactos
   - Marca el primer email como "No es spam"
   - Crea un filtro para que emails de Formspree vayan a bandeja de entrada:
     * Gmail: Configuración → Filtros → Nuevo filtro
     * De: formspree.io → Crear filtro → "Nunca enviar a spam"

4. **SPF/DKIM (Avanzado - si tienes dominio propio)**:
   - Contacta con tu proveedor de hosting
   - Añade registros SPF que incluyan Formspree
   - Ejemplo SPF: `v=spf1 include:formspree.io ~all`

## Características del formulario:

✅ Validación de campos requeridos
✅ Protección anti-spam (honeypot mejorado)
✅ Campo de asunto para categorización
✅ Asunto personalizado en emails
✅ Mensajes de éxito/error
✅ Animación de carga
✅ Responsive design
✅ Metadata optimizada para evitar spam

## ⚠️ IMPORTANTE: Evitar que emails lleguen a SPAM

**Lee el archivo EVITAR-SPAM.md** para la guía completa sobre cómo configurar Formspree correctamente y evitar que los mensajes lleguen a spam.

Resumen rápido:
- Configura "From Name" en Formspree
- Activa reCAPTCHA
- Añade formspree.io a tus contactos
- Crea filtro "Nunca enviar a spam" en Gmail/Outlook

## Alternativa: Web3Forms

Si prefieres otra opción gratuita:
1. Ve a: https://web3forms.com/
2. Ingresa tu email
3. Obtén tu Access Key
4. Cambia el action a: `action="https://api.web3forms.com/submit"`
5. Añade un campo hidden: `<input type="hidden" name="access_key" value="TU_ACCESS_KEY">`

## ¿Problemas?

Si tienes problemas con el formulario:
- Verifica que el Form ID esté correctamente copiado
- Comprueba la consola del navegador (F12) para ver errores
- Asegúrate de que el sitio esté publicado en un dominio público
