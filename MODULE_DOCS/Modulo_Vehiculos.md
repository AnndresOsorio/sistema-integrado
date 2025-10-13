# Módulo: Vehículos

## Descripción General
El módulo **Vehículos** gestiona el inventario de automóviles disponibles para venta, actualizando existencias según las transacciones realizadas.

---

## Funcionalidad
| Código | Descripción | Tipo de usuario |
|---------|--------------|-----------------|
| RF04 | Mostrar disponibilidad de vehículos | Todos |
| RF06 | Registrar ventas de vehículos | Empleado |
| RF07 | Actualizar inventario automáticamente | Sistema |
| RF15 | Transferir vehículos entre sucursales | Administrador |

---

## Datos de Entrada
| Campo | Tipo | Descripción | Validaciones |
|--------|------|-------------|---------------|
| id_vehiculo | INT | Identificador único | Autoincremental |
| marca | VARCHAR | Marca del vehículo | Requerido |
| modelo | VARCHAR | Modelo o versión | Requerido |
| precio | DECIMAL | Precio de venta | > 0 |
| stock | INT | Cantidad disponible | >= 0 |

---

## Datos de Salida
| Salida | Descripción |
|---------|--------------|
| Inventario actualizado | Cantidades reflejadas tras ventas |
| Vehículos agotados | Estado visible en la interfaz |
| Reportes de ventas | Exportables a PDF o Excel |

---

## Pruebas
| Tipo | Descripción | Resultado |
|------|--------------|-----------|
| Unit Test | Registrar vehículo | Guardado correcto |
| Integration | Venta → Descuento stock | Stock actualizado |
| Functional | Mostrar vehículos agotados | Estado visible al usuario |

---

## Configuración
- **Tabla:** `vehiculos`
- **Conexión:** MySQL Docker
- **API REST:** `/api/vehiculos/**`
- **Dependencias:** Spring Boot Data JPA

---

## Estado del Módulo
**Versión:** 1.0  
**Responsables:** Andrés Osorio, Kevin Barreto  
**Última actualización:** 12/10/2025
