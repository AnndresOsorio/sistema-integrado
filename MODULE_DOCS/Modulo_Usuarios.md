# Módulo: Usuarios

## Descripción General
El módulo **Usuarios** gestiona la autenticación, registro y administración de roles dentro del sistema **Autonova S.A.**  
Permite a los administradores crear, modificar y eliminar cuentas de empleados o clientes, y asignarles los permisos correspondientes.

---

## Funcionalidad
| Código | Descripción | Tipo de usuario |
|---------|--------------|-----------------|
| RF01 | Controlar el inicio de sesión según rol | Todos |
| RF05 | Permitir asignar roles a empleados | Administrador |
| RF11 | Historial de actividad por usuario | Administrador |

---

## Datos de Entrada
| Campo | Tipo de Dato | Descripción | Validaciones |
|--------|---------------|-------------|---------------|
| usuario | String | Nombre de usuario o correo | Requerido, único |
| contraseña | String | Contraseña encriptada | Mínimo 8 caracteres |
| rol | Enum | Tipo de usuario (`ADMIN`, `EMPLEADO`, `CLIENTE`) | Obligatorio |

---

## Datos de Salida
| Salida | Descripción |
|---------|--------------|
| Token JWT | Permite mantener la sesión activa |
| Mensajes de validación | Indica errores o resultados de las operaciones |
| Listado de usuarios | Devuelve todos los usuarios registrados (solo admin) |

---

## Pruebas del Módulo

| Tipo de Prueba | Descripción | Resultado Esperado |
|----------------|--------------|--------------------|
| Unit Test | Validar creación de usuario con datos válidos | Usuario creado correctamente |
| Unit Test | Validar login con credenciales incorrectas | Mensaje de error |
| Integration Test | Verificar asignación de roles y acceso por rol | Solo usuarios autorizados acceden |
| Functional Test | Login → Crear usuario → Consultar usuarios | Flujo exitoso sin errores |

---

## Configuración del Entorno
- **Base de datos:** MySQL (Docker)
- **Tabla:** `usuarios`
- **Conexión:** `jdbc:mysql://localhost:3307/autonova_db`
- **Puerto API:** 8080
- **Dependencias:** Spring Security, Spring Data JPA

---

## Observaciones
- Todas las contraseñas se almacenan usando **BCrypt**.
- Se aplican restricciones de acceso mediante **Spring Security**.
- Módulo probado con JUnit 5 y Postman.

---

## Estado del Módulo
**Versión:** 1.0  
**Responsables:** Andrés Osorio, Kevin Barreto  
**Última actualización:** 12/10/2025
