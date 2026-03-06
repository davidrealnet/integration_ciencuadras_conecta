# 🏢 Ecosistema API Inmobiliario Bolívar  
## Integración Ciencuadras + Conecta (Insomnia)

Este repositorio contiene la base de trabajo para la integración de servicios API relacionados con:

- **Ciencuadras / WS Listing**  
  Publicación, actualización y consulta de inmuebles.
- **Conecta / Estudio de Arrendamiento**  
  Creación, actualización, consulta y validación de solicitudes de estudio.

El objetivo de este proyecto es centralizar en un solo lugar la documentación funcional, la configuración de ambientes y la colección de requests para pruebas, validación técnica y futuras integraciones con sistemas como **Odoo**.

---

# 📁 Contenido del repositorio

Este repositorio puede incluir archivos como:

- `README.md`  
  Documento principal de guía del proyecto.
- `insomnia-config.json`  
  Archivo exportado desde Insomnia con la estructura del proyecto, requests, carpetas y entornos.
- `/docs`  
  Carpeta con manuales técnicos, PDFs y documentación de referencia.
- `/src`
  Carpeta opcional para ejemplos de implementación o scripts auxiliares.

---

# 📦 ¿Qué contiene el archivo exportado de Insomnia?

El archivo exportado desde Insomnia contiene la estructura base del proyecto API, incluyendo:

- Carpetas organizadas por funcionalidad
- Requests HTTP
- Variables de entorno
- Configuración de ambientes
- Headers, bodies y endpoints base
- Flujo inicial para autenticación y pruebas

La colección está orientada a manejar dos grandes grupos:

## 1. 🏠 Ciencuadras / WS Listing
Incluye pruebas para:
- Login
- Creación de inmuebles
- Actualización de inmuebles
- Consulta de estado
- Consulta de inmueble por código
- Consultas auxiliares y operativas

## 2. 📄 Conecta / Estudio de Arrendamiento
Incluye pruebas para:
- OAuth / generación de token
- Creación o actualización de estudio
- Consulta de estado
- Flujo OTP
- Consulta de formularios
- Gestión de anexos y documentos

---

# ⬇️ Cómo importar el archivo en Insomnia

## Opción 1: importar desde archivo JSON
1. Abrir **Insomnia**.
2. En el menú principal seleccionar **Import / Export**.
3. Elegir **Import Data**.
4. Seleccionar **From File**.
5. Buscar el archivo exportado, por ejemplo:
   - `insomnia-project.json`
6. Confirmar la importación.
7. Verificar que aparezcan:
   - carpetas
   - requests
   - entornos
   - variables

---

# ✅ Recomendación después de importar

Una vez importado el proyecto, se recomienda revisar primero los **entornos** y las **variables** antes de ejecutar cualquier request.

## Validar:
- URLs base
- Tokens
- Credenciales
- API keys
- Canales o identificadores configurables
- Variables funcionales como códigos, consecutivos, ids y fechas

---

# 🌍 Estructura sugerida de entornos

El proyecto está pensado para trabajar con los siguientes ambientes:

- **DEV**
- **STG**
- **PROD**

## Uso recomendado
- **DEV**: pruebas técnicas y desarrollo
- **STG**: validaciones previas a producción
- **PROD**: ambiente real

---

# 🔑 Variables importantes a revisar

Dependiendo del flujo, algunas variables deben completarse manualmente antes de probar:

## Ciencuadras
- `ws_listing_login_url`
- `ws_listing_base_url`
- `ws_listing_username`
- `ws_listing_password`
- `ws_listing_token`
- `property_code`
- `ws_listing_request_id`
- `integrator`

## Conecta
- `conecta_token_url`
- `conecta_base_url`
- `conecta_basic_auth`
- `conecta_access_token`
- `conecta_api_key`
- `conecta_channel`
- `consecutive`
- `x_auth`
- `conecta_solicitud_id`
- `otp_code`
- `fecha_inicio`
- `fecha_fin`
- `estado`

---

# 🔄 Flujo sugerido de uso

## Para Ciencuadras
1. Configurar credenciales
2. Ejecutar login
3. Guardar token
4. Probar requests operativos
5. Validar respuestas y códigos de estado

## Para Conecta
1. Configurar token URL y credenciales OAuth
2. Obtener access token
3. Ejecutar `save-form`
4. Guardar `consecutive` y `x_auth`
5. Probar consulta de estado y flujo OTP si aplica

---

# ⚠️ Recomendaciones importantes

## 1. No usar producción para pruebas iniciales
Las primeras validaciones deben hacerse en **DEV** o **STG**.

## 2. No dejar credenciales sensibles en texto plano
Evitar subir al repositorio:
- usuarios reales
- contraseñas reales
- tokens vigentes
- secrets productivos

## 3. Versionar cambios de forma ordenada
Si el proyecto se sigue trabajando en Git, se recomienda:
- hacer commits pequeños
- documentar los cambios
- no mezclar ajustes de entornos con cambios funcionales grandes

## 4. Validar manuales técnicos
La colección base puede requerir ajustes finos según:
- cambios del proveedor
- actualización de endpoints
- parámetros nuevos
- reglas funcionales del negocio

---

# 🛠 Casos en los que puede requerir ajustes

Este archivo exportado es una **base de trabajo**, por lo tanto puede necesitar ajustes cuando:

- cambian endpoints
- cambian credenciales
- cambian reglas de autenticación
- se agregan nuevos servicios
- se modifica el payload esperado
- se cambia el flujo entre ambientes

---

# 📌 Buenas prácticas recomendadas

- Separar claramente requests de Ciencuadras y Conecta
- Mantener variables genéricas en la base
- Definir URLs y credenciales por ambiente
- No quemar datos reales en el proyecto
- Documentar cualquier endpoint nuevo que se agregue
- Probar autenticación antes de probar lógica de negocio

---

# 🧭 Posible estructura funcional del proyecto

```text
00 - Auth
01 - Ciencuadras WS Listing
02 - Conecta Estudio
03 - Consulta Estado
04 - Utilities
