# Regalos_TalentUO24-25

**Entrega final del curso de Programación de Aplicaciones Web y Bases de Datos TalentUO (2024-2025)**

---

## Introducción

Este proyecto es el resultado final del curso y tiene como objetivo demostrar el dominio de las tecnologías y conceptos aprendidos, integrando conocimientos de diseño de bases de datos, desarrollo de aplicaciones backend con Node.js y Express, y desarrollo frontend con React utilizando componentes avanzados. 

La aplicación desarrollada es una **plataforma de listas de regalos**, donde los usuarios pueden gestionar sus deseos, compartirlos con amigos y colaborar en la elección de regalos de manera organizada y transparente.

---

## Descripción general del proyecto

La temática principal del proyecto se centra en permitir a los usuarios:
1. Crear y gestionar listas de regalos que desean recibir.
2. Compartir estas listas con amigos seleccionados.
3. Consultar y elegir regalos de las listas de amigos.
4. Garantizar la seguridad y privacidad mediante autenticación basada en JWT.

Además de las funcionalidades descritas, el desarrollo incluye requisitos específicos sobre la arquitectura y el diseño del sistema, cumpliendo con estándares modernos de desarrollo web.

---

## Funcionalidades detalladas

### **Gestión de usuarios**
1. **Registro de usuarios**:
   - Endpoint: `POST /users/`.
   - Permite registrar un nuevo usuario proporcionando:
     - Email (debe ser único en la base de datos).
     - Nombre.
     - Contraseña (mínimo 5 caracteres).
   - Realiza validaciones de entrada y genera errores claros en caso de conflictos, como un email ya registrado.

2. **Inicio de sesión**:
   - Endpoint: `POST /users/login/`.
   - Autentica a los usuarios mediante sus credenciales y genera un **JWT**.
   - Este token se almacena en una lista de claves activas y permite acceder a endpoints protegidos.

3. **Cierre de sesión**:
   - Endpoint: `POST /users/disconnect/`.
   - Elimina el token activo de la lista, garantizando que el usuario queda desconectado.

---

### **Gestión de regalos**
1. **Crear regalo**:
   - Endpoint: `POST /presents/`.
   - Permite crear un regalo asociado al usuario autenticado. Los campos requeridos son:
     - Nombre.
     - Descripción.
     - URL del regalo.
     - Precio.
   - Cada regalo incluye un campo adicional `chosenBy`, inicialmente vacío, que se actualizará cuando un amigo decida regalarlo.

2. **Modificar regalo**:
   - Endpoint: `PUT /presents/:id`.
   - Permite al creador del regalo actualizar sus datos:
     - Nombre.
     - Descripción.
     - URL.
     - Precio.
   - Se valida que el usuario autenticado sea el creador del regalo.

3. **Eliminar regalo**:
   - Endpoint: `DELETE /presents/:id`.
   - Elimina un regalo creado por el usuario autenticado, asegurando que no se afecta información de otros usuarios.

4. **Listar regalos del usuario**:
   - Endpoint: `GET /presents/`.
   - Devuelve todos los regalos creados por el usuario autenticado.

5. **Ver detalle de un regalo**:
   - Endpoint: `GET /presents/:id`.
   - Retorna la información de un regalo específico, siempre que pertenezca al usuario autenticado.

---

### **Gestión de amigos**
1. **Agregar a un amigo**:
   - Endpoint: `POST /friends/`.
   - Permite añadir el correo electrónico de un amigo a la lista del usuario autenticado.
   - No se requiere confirmación por parte del amigo.

2. **Listar amigos**:
   - Endpoint: `GET /friends/`.
   - Devuelve la lista completa de amigos del usuario autenticado.

3. **Eliminar a un amigo**:
   - Endpoint: `DELETE /friends/:email`.
   - Elimina un amigo de la lista del usuario autenticado utilizando su correo electrónico.

---

### **Interacciones con listas de regalos de amigos**
1. **Consultar regalos de un amigo**:
   - Endpoint: `GET /presents?userEmail=<email>`.
   - Permite a un usuario autenticado ver los regalos de un amigo, siempre que:
     - El amigo lo haya añadido a su lista.
     - Los regalos sean accesibles según la relación de amistad.

2. **Seleccionar un regalo para regalarlo**:
   - Extensión del endpoint: `PUT /presents/:id`.
   - Si el usuario no es el creador del regalo pero cumple con las condiciones de amistad, puede marcar un regalo como "elegido". 
   - Condiciones:
     - Debe existir una relación de amistad válida.
     - El regalo no debe estar previamente reservado por otro usuario.
     - El creador del regalo no puede seleccionarlo para sí mismo.

---

## Detalles técnicos

### **Backend**
- **Estructura**:
  - Organización del proyecto en módulos con uso de routers.
  - Implementación de middleware para proteger rutas sensibles.
- **Validaciones**:
  - Control de datos de entrada en todos los endpoints.
  - Gestión de errores lógicos, como intentos de registro duplicados o accesos no autorizados.
- **Seguridad**:
  - Uso de JWT para autenticar y proteger las rutas.
  - Verificación estricta de permisos antes de realizar modificaciones.

### **Frontend**
- **Framework**: React.
- **Componentes de UI**: Ant Design.
  - Componentes utilizados: Layout, Menu, Card, Input, Button, Table, List, Descriptions, Notifications.
  - Diseño moderno e intuitivo con opciones de personalización.
- **Validaciones**:
  - Validación de campos en formularios del lado cliente.
  - Muestra de mensajes claros para errores enviados desde el backend.
- **Experiencia de Usuario**:
  - Redirecciones automáticas tras realizar acciones exitosas.
  - Notificaciones visuales al completar tareas.

---

## Base de datos

### **Tablas clave**
1. **Users**: 
   - Registra información básica de los usuarios.
   - Claves principales: `id`, `email`, `name`, `password`.
2. **Presents**: 
   - Gestiona los regalos creados por los usuarios.
   - Campos clave: `id`, `userId`, `name`, `description`, `url`, `price`, `chosenBy`.
3. **Friends**: 
   - Relaciona usuarios con sus amigos.
   - Campos clave: `emailMainUser`, `emailFriend`.

---

## Información detallada

Para más información, la documentación y los requisitos funcionales se encuentran en el archivo **Requisitos_TalentUO_24-25** en el directorio raíz de éste repositorio.
