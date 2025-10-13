# Módulo: Venta de Vehículos

## Descripción General
Permite gestionar las ventas de vehículos nuevos y usados, generando facturas y actualizando automáticamente los inventarios.

---

## Funcionalidad
| Código | Descripción | Tipo de usuario |
|---------|--------------|-----------------|
| RF06 | Registrar venta de vehículo | Empleado |
| RF07 | Actualizar inventario tras venta | Sistema |
| RF14 | Crear facturas de transacción | Empleado |

---

## Datos de Entrada
| Campo | Tipo | Descripción | Validaciones |
|--------|------|-------------|---------------|
| id_venta | INT | Identificador | Autoincremental |
| id_vehiculo | INT | Vehículo vendido | Relación foránea |
| cliente | VARCHAR | Nombre del comprador | Requerido |
| valor | DECIMAL | Valor final | > 0 |
| fecha | DATE | Fecha de la transacción | Automática |

---

## Datos de Salida
| Salida | Descripción |
|---------|--------------|
| Factura PDF | Documento generado automáticamente |
| Inventario actualizado | Vehículo descontado |
| Registro de garantía | Asociado automáticamente |

---

## Pruebas
| Tipo | Descripción | Resultado |
|------|--------------|-----------|
| Unit Test | Registrar venta | Exitosa |
| Integration | Venta → Garantía → Inventario | Flujo correcto |
| Functional | Descargar factura | Archivo PDF correcto |

---

## Configuración
- **Tabla:** `ventas_vehiculos`
- **API REST:** `/api/ventas/vehiculos/**`
- **Dependencias:** Spring Boot JPA, Spring Web, JasperReports

---

## Estado del Módulo
**Versión:** 1.0  
**Responsables:** Andrés Osorio, Kevin Barreto  
**Última actualización:** 12/10/2025
