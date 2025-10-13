# Módulo: Sucursales

## Descripción General
Administra la información de las sucursales, incluyendo ubicación, contacto, inventario y personal asociado.  
Permite registrar, modificar y eliminar sucursales, así como visualizar su información en el sistema.

---

## Funcionalidad
| Código | Descripción | Tipo de usuario |
|---------|--------------|-----------------|
| RF02 | Crear, modificar y eliminar sucursales | Administrador |
| RF03 | Mostrar información y contacto de sucursales | Todos |
| RF15 | Transferencia de vehículos/repuestos entre sucursales | Administrador |

---

## Datos de Entrada
| Campo | Tipo de Dato | Descripción | Validaciones |
|--------|---------------|-------------|---------------|
| id_sucursal | INT | Identificador único | Autoincremental |
| nombre | VARCHAR | Nombre de la sucursal | Obligatorio |
| direccion | VARCHAR | Dirección física | Obligatorio |
| telefono | VARCHAR | Contacto | Validar formato |
| responsable | VARCHAR | Encargado de la sucursal | Requerido |

---

## Datos de Salida
| Salida | Descripción |
|---------|--------------|
| Listado de sucursales | Todas las sucursales registradas |
| Detalle de sucursal | Información completa de contacto e inventario |

---

## Pruebas del Módulo
| Tipo | Descripción | Resultado Esperado |
|------|--------------|--------------------|
| Unit Test | Crear nueva sucursal | Registro exitoso |
| Integration Test | Actualizar datos de sucursal | Cambios persistidos |
| Functional Test | Mostrar lista de sucursales | Visualización correcta |

---

## Configuración
- **Tabla:** `sucursales`
- **Puerto API:** `/api/sucursales/**`
- **Dependencias:** Spring Boot Web, JPA, Lombok

---

## Estado del Módulo
**Versión:** 1.0  
**Responsables:** Andrés Osorio, Kevin Barreto  
**Última actualización:** 12/10/2025
