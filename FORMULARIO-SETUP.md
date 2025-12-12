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

### 5. Configurar notificaciones (opcional)
En el panel de Formspree puedes:
- Cambiar el email donde recibirás los mensajes
- Personalizar mensajes de confirmación
- Añadir validación anti-spam
- Configurar webhooks

## Características del formulario:

✅ Validación de campos requeridos
✅ Protección anti-spam (honeypot)
✅ Mensajes de éxito/error
✅ Animación de carga
✅ Responsive design
✅ Los usuarios recibirán los emails en el correo configurado en Formspree

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
