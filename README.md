# Regalos_TalentUO24-25

**Entrega final del curso de Programación de Aplicaciones Web y Bases de Datos TalentUO (2024-2025)**

## Aplicación de listas de regalos

### Descripción del proyecto
Esta aplicación web permite a los usuarios gestionar listas de regalos, con funcionalidades avanzadas que facilitan tanto la creación de listas personales como la interacción social con amigos. 
El propósito principal es ofrecer un entorno intuitivo y dinámico donde los usuarios puedan organizar regalos que desean recibir y coordinar con sus amigos para hacer regalos de manera sencilla y segura.

---

### Funcionalidades Principales

#### **Gestión de usuarios**
- **Registro de usuarios**: 
  Los usuarios pueden registrarse proporcionando un correo electrónico, nombre y contraseña. Se valida que el email sea único y que la contraseña cumpla con un estándar mínimo de seguridad (5 caracteres).
- **Inicio de sesión**: 
  Autenticación mediante JWT (JSON Web Token) para sesiones seguras.
- **Cierre de sesión**: 
  Finalización de la sesión del usuario y eliminación del token activo.

#### **Gestión de regalos**
- **Crear regalos**: 
  Los usuarios pueden registrar regalos especificando nombre, descripción, URL y precio.
- **Modificar regalos**: 
  Actualización de los datos de regalos creados por el usuario.
- **Eliminar regalos**: 
  Eliminar regalos de la lista personal.
- **Listar regalos**: 
  Visualización de todos los regalos creados por el usuario autenticado.
- **Compartir regalos con amigos**: 
  Los usuarios pueden seleccionar regalos de otros amigos para regalarlos, quedando registrados como responsables de ese regalo.

#### **Gestión de amigos**
- **Agregar amigos**: 
  Los usuarios pueden añadir correos electrónicos de amigos para compartir sus listas de regalos.
- **Listar amigos**: 
  Visualizar los amigos agregados a la lista del usuario.
- **Eliminar amigos**: 
  Eliminar contactos de la lista de amigos.

#### **Interacciones con las listas de regalos de amigos**
- **Ver regalos de amigos**: 
  Los usuarios pueden consultar las listas de regalos de sus amigos si están autorizados.
- **Seleccionar regalos**: 
  Reservar regalos de amigos para marcarlos como "elegidos" y evitar duplicidades.

---

### Tecnologías utilizadas

#### **Backend**
- **Framework**: Node.js con Express.
- **Autenticación**: JWT para gestionar sesiones.
- **Base de datos**: MySQL para almacenamiento de datos persistentes.
- **Validaciones**: Control exhaustivo de entradas y respuestas de API con mensajes de error adecuados.

#### **Frontend**
- **Framework**: React.
- **Librería de componentes**: Ant Design (incluyendo Layout, Menu, Card, Table, etc.).
- **Estilo**: Personalización y uso estándar de componentes gráficos modernos.
- **Validaciones**: Validación de entradas directamente en el cliente, mostrando errores de manera clara.

---

### Base de datos

#### **Tablas principales**
1. **Users**: Gestiona la información básica de los usuarios registrados.
2. **Presents**: Registra los regalos creados por los usuarios.
3. **Friends**: Relaciona a los usuarios con sus amigos para compartir listas de regalos.
