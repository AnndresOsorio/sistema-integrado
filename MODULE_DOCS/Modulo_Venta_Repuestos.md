# Módulo: Venta de Repuestos

## Descripción General
Gestiona el registro, actualización y control del inventario de repuestos en cada sucursal.  
Permite realizar ventas, controlar existencias y emitir alertas cuando los productos se agotan.

---

## Funcionalidad
| Código | Descripción | Tipo de usuario |
|---------|--------------|-----------------|
| RF08 | Mostrar disponibilidad de repuestos | Todos |
| RF09 | Registrar venta de repuestos | Empleado |
| RF10 | Actualizar inventario automáticamente | Sistema |

---

## Datos de Entrada
| Campo | Tipo | Descripción | Validaciones |
|--------|------|-------------|---------------|
| id_repuesto | INT | Identificador | Autoincremental |
| nombre | VARCHAR | Nombre del repuesto | Requerido |
| categoria | VARCHAR | Tipo de repuesto | Opcional |
| precio | DECIMAL | Valor de venta | > 0 |
| stock | INT | Existencia | >= 0 |

---

## Datos de Salida
| Salida | Descripción |
|---------|--------------|
| Stock actualizado | Después de la venta |
| Factura generada | PDF con detalles de compra |
| Alerta de agotamiento | Notificación interna |

---

## Pruebas
| Tipo | Descripción | Resultado |
|------|--------------|-----------|
| Unit Test | Registrar venta | Correcta |
| Integration | Descuento de stock | Actualizado |
| Functional | Mostrar alerta agotado | Visible |

---

## Configuración
- **Tabla:** `repuestos`
- **API REST:** `/api/repuestos/**`
- **Dependencias:** Spring Boot JPA, Thymeleaf

---

## Estado del Módulo
**Versión:** 1.0  
**Responsables:** Andrés Osorio, Kevin Barreto  
**Última actualización:** 12/10/2025
