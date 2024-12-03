# Regalos_TalentUO24-25
Entrega final del curso de Programación de Aplicaciones Web y Bases de Datos TalentUO (2024-2025)

Aplicación de Listas de Regalos
Descripción del Proyecto
Esta aplicación web permite a los usuarios gestionar listas de regalos, con funcionalidades avanzadas que facilitan tanto la creación de listas personales como la interacción social con amigos. El propósito principal es ofrecer un entorno intuitivo y dinámico donde los usuarios puedan organizar regalos que desean recibir y coordinar con sus amigos para hacer regalos de manera sencilla y segura.

Funcionalidades Principales
Gestión de Usuarios
Registro de Usuarios: Los usuarios pueden registrarse proporcionando un correo electrónico, nombre y contraseña. Se valida que el email sea único y que la contraseña cumpla con un estándar mínimo de seguridad (5 caracteres).
Inicio de Sesión: Autenticación mediante JWT (JSON Web Token) para sesiones seguras.
Cierre de Sesión: Finalización de la sesión del usuario y eliminación del token activo.
Gestión de Regalos
Crear Regalos: Los usuarios pueden registrar regalos especificando nombre, descripción, URL y precio.
Modificar Regalos: Actualización de los datos de regalos creados por el usuario.
Eliminar Regalos: Eliminar regalos de la lista personal.
Listar Regalos: Visualización de todos los regalos creados por el usuario autenticado.
Compartir Regalos con Amigos: Los usuarios pueden seleccionar regalos de otros amigos para regalarlos, quedando registrados como responsables de ese regalo.
Gestión de Amigos
Agregar Amigos: Los usuarios pueden añadir correos electrónicos de amigos para compartir sus listas de regalos.
Listar Amigos: Visualizar los amigos agregados a la lista del usuario.
Eliminar Amigos: Eliminar contactos de la lista de amigos.
Interacciones con las Listas de Regalos de Amigos
Ver Regalos de Amigos: Los usuarios pueden consultar las listas de regalos de sus amigos si están autorizados.
Seleccionar Regalos: Reservar regalos de amigos para marcarlos como "elegidos" y evitar duplicidades.
Tecnologías Utilizadas
Backend
Framework: Node.js con Express.
Autenticación: JWT para gestionar sesiones.
Base de Datos: MySQL para almacenamiento de datos persistentes.
Validaciones: Control exhaustivo de entradas y respuestas de API con mensajes de error adecuados.
Frontend
Framework: React.
Librería de Componentes: Ant Design (incluyendo Layout, Menu, Card, Table, etc.).
Estilo: Personalización y uso estándar de componentes gráficos modernos.
Validaciones: Validación de entradas directamente en el cliente, mostrando errores de manera clara.
Base de Datos
Tablas Principales
Users: Gestiona la información básica de los usuarios registrados.
Presents: Registra los regalos creados por los usuarios.
Friends: Relaciona a los usuarios con sus amigos para compartir listas de regalos.
