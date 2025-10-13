# MANUAL TÉCNICO — AUTONOVA S.A.

## Descripción General
**Autonova S.A.** es un sistema de gestión de sucursales de compra y venta de vehículos, desarrollado en **Java Spring Boot** con base de datos **MySQL**.  
Permite controlar el inventario de vehículos y repuestos, gestionar usuarios por roles y registrar las operaciones de compra, venta y mantenimiento.

Este documento describe la **arquitectura técnica**, la **configuración de entornos**, las **dependencias**, las **pruebas** y los **requisitos técnicos** necesarios para ejecutar el sistema correctamente.

---

## Arquitectura del Sistema

El sistema sigue el modelo **MVC (Modelo–Vista–Controlador)** y está compuesto por los siguientes módulos:

| Módulo | Descripción |
|--------|--------------|
| **Autenticación** | Control de inicio de sesión, asignación de roles (admin, asesor, cliente). |
| **Sucursales** | CRUD de sucursales (crear, modificar, eliminar, listar). |
| **Vehículos y Repuestos** | Registro, disponibilidad, inventario y alertas de stock. |
| **Ventas y Facturación** | Registro de ventas, generación de facturas, historial. |
| **Reportes** | Estadísticas de ventas, inventario y transferencias entre sucursales. |

---

## Tecnologías Utilizadas

| Componente | Tecnología |
|-------------|-------------|
| Lenguaje | Java 17 |
| Framework | Spring Boot 3.x |
| ORM | Spring Data JPA / Hibernate |
| Base de datos | MySQL 8 |
| Servidor embebido | Apache Tomcat (Spring Boot default) |
| Control de versiones | Git / GitHub |
| IDE recomendado | IntelliJ IDEA / Eclipse |
| Pruebas | JUnit 5 |
| Contenedores | Docker y Docker Compose |

---

## Configuración de la Base de Datos

### Archivo de configuración: `src/main/resources/application.properties`

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/autonova_db
spring.datasource.username=root
spring.datasource.password=tu_contraseña
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
server.port=8080

---

## Configuración de Contenedores Docker

Objetivo:
Permitir la ejecución del sistema Autonova S.A. en un entorno aislado y reproducible, utilizando contenedores Docker para la aplicación y la base de datos MySQL.

Estructura de Contenedores
Servicio	Descripción	Imagen	Puerto local	Puerto interno
autonova_app	Contenedor principal con la aplicación Java Spring Boot	openjdk:17	8080	8080
autonova_db	Contenedor de base de datos MySQL	mysql:8.0	3307	3306