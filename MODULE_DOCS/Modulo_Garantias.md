# Módulo: Garantías

## Descripción General
El módulo **Garantías** permite registrar, consultar y hacer seguimiento a las garantías ofrecidas con cada vehículo vendido.  
Garantiza trazabilidad sobre los plazos, estado y reclamaciones asociadas a las ventas realizadas.

---

## Funcionalidad
| Código | Descripción | Tipo de usuario |
|---------|--------------|-----------------|
| RF12 | Mostrar la garantía según el vehículo vendido | Empleado / Cliente |
| RF13 | Permitir seguimiento a la garantía | Empleado / Administrador |

---

## Datos de Entrada
| Campo | Tipo de Dato | Descripción | Validaciones |
|--------|---------------|-------------|---------------|
| id_venta | INT | Identificador de la venta | Requerido |
| fecha_inicio | DATE | Fecha de inicio de la garantía | Requerido |
| fecha_fin | DATE | Fecha de finalización | Calculado automáticamente |
| estado | ENUM | “Activa”, “Vencida”, “Reclamada” | Obligatorio |

---

## Datos de Salida
| Salida | Descripción |
|---------|--------------|
| Estado de la garantía | Muestra si está activa o vencida |
| Historial de reclamaciones | Listado de solicitudes del cliente |
| Notificación de vencimiento | Alerta generada automáticamente |

---

## Pruebas del Módulo
| Tipo | Descripción | Resultado Esperado |
|------|--------------|--------------------|
| Unit Test | Registrar garantía | Se almacena correctamente |
| Unit Test | Consultar garantía vencida | Se muestra estado “Vencida” |
| Integration Test | Asociar garantía a venta | Relación correcta en la BD |
| Functional Test | Flujo venta → garantía | Generación automática exitosa |

---

## Configuración
- **Tabla:** `garantias`
- **Dependencias:** Spring Data JPA
- **Conexión:** `jdbc:mysql://localhost:3307/autonova_db`
- **Servicios REST:** `/api/garantias/**`

---

## Estado del Módulo
**Versión:** 1.0  
**Responsables:** Andrés Osorio, Kevin Barreto  
**Última actualización:** 12/10/2025
