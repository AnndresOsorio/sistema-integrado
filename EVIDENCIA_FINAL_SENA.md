# EVIDENCIA FINAL – GA8-220501096-AA1-EV02  
## MÓDULOS INTEGRADOS – AUTONOVA S.A.

---

## 1. Descripción del Sistema

**Autonova S.A.** es un sistema integral desarrollado en **Java Spring Boot** con **MySQL**, que permite la gestión de sucursales dedicadas a la compra y venta de vehículos, repuestos y servicios postventa.

El sistema integra módulos de usuarios, vehículos, repuestos, garantías, ventas de vehiculos y venta de repuestos, asegurando la trazabilidad completa de la información empresarial.

---

## 2. Requerimientos del Sistema

### 2.1 Requerimientos Funcionales
| ID | Descripción | Prioridad |
|----|--------------|------------|
| RF01 | Control de inicio de sesión y roles de usuario | Alta |
| RF02 | Registro, modificación y eliminación de sucursales | Alta |
| RF03 | Mostrar información básica y de contacto de las sucursales | Media |
| RF04 | Actualización automática de inventarios de vehículos y repuestos | Alta |
| RF05 | Registro y control de ventas de vehículos y repuestos | Alta |
| RF06 | Programación y cancelación de citas de mantenimiento | Alta |
| RF07 | Envío de alertas al personal cuando existencias estén por agotarse | Media |
| RF08 | Generación de reportes y facturas | Alta |

### 2.2 Requerimientos No Funcionales
| ID | Descripción | Prioridad |
|----|--------------|------------|
| RNF01 | Seguridad y manejo de roles | Alta |
| RNF02 | Interfaz intuitiva y responsive | Alta |
| RNF03 | Tiempo de respuesta inferior a 4 segundos | Media |
| RNF04 | Compatibilidad con navegadores comunes | Media |
| RNF05 | Documentación técnica completa | Alta |

---

## 3. Arquitectura General del Sistema

**Arquitectura multicapa (MVC)**:

Frontend (Thymeleaf / HTML / CSS / JS)
↓
Backend (Java Spring Boot)
↓
Base de datos (MySQL)

**Contenedorización:**  
Todo el entorno de ejecución se administra mediante **Docker Compose**, con dos servicios principales:
- `autonova_app`: Aplicación Spring Boot (puerto 8080)
- `autonova_db`: Base de datos MySQL (puerto 3307)

---

## 4. Configuración del Entorno (Docker)

Archivo: `docker-compose.yml`

services:
  db:
    image: mysql:8.0
    container_name: autonova_db
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: root
      MYSQL_DATABASE: autonova
    ports:
      - "3307:3306"
    volumes:
      - db_data:/var/lib/mysql

  app:
    image: openjdk:17
    container_name: autonova_app
    working_dir: /app
    volumes:
      - ./build:/app
    ports:
      - "8080:8080"
    depends_on:
      - db

volumes:
  db_data:
Comandos utilizados:


docker-compose up -d        # Levantar los contenedores
docker ps                   # Verificar contenedores activos
docker-compose down         # Detener y eliminar contenedores
Resultado:
Contenedores creados y corriendo:

autonova_app    ->  puerto 8080
autonova_db     ->  puerto 3307
5. Pruebas Realizadas
5.1 Pruebas Unitarias
Ejecutadas con JUnit 5:

Módulo	Prueba	Resultado
Usuarios	Validar creación y login de usuario	- Exitosa
Vehículos	Registro y actualización de inventario	- Exitosa
Ventas	Generación de factura y actualización de stock	- Exitosa

5.2 Pruebas de Integración (Postman)
Endpoint	Método	Descripción	Estado
/api/login	POST	Autenticación de usuario	- OK
/api/sucursales	GET	Consulta de todas las sucursales	- OK
/api/vehiculos	POST	Registro de vehículo nuevo	- OK
/api/repuestos	PUT	Actualización de inventario	- OK
/api/ventas	GET	Generar reporte de ventas	- OK

6. Ambientes de Desarrollo y Pruebas
Ambiente	Descripción	Configuración
Desarrollo	Entorno local con Spring Boot + MySQL Dockerizado	localhost:8080
Pruebas	Validación con Postman sobre API REST	Colección Postman con endpoints principales

7. Documentación de Módulos
Todos los módulos se documentan dentro del directorio /MODULE_DOCS/, cada uno con su estructura:

Descripción general

Campos de entrada y salida

Ejemplo JSON (si aplica)

Casos de prueba unitarios

Resultados esperados

Ejemplos:

/MODULE_DOCS/Modulo_Usuarios.md
/MODULE_DOCS/Modulo_Sucursales.md
/MODULE_DOCS/Modulo_Vehiculos.md
/MODULE_DOCS/Modulo_Garantias.md
/MODULE_DOCS/Modulo_Venta_Repuestos.md
/MODULE_DOCS/Modulo_Venta_Vehiculos.md
8. Archivos Incluidos en la Entrega
Tipo	Ubicación
Código fuente	/src/
Documentación general	/docs/
Documentación técnica	/MANUAL_TECNICO.md
Guía de instalación	/INSTALL.md
Documentación por módulo	/MODULE_DOCS/
Ejecutables (.jar)	/build/
Archivos compilados finales	/executables/
Evidencia final	/EVIDENCIA_FINAL_SENA.md


9. Conclusión
El proyecto Autonova S.A. cumple con los requerimientos establecidos en la evidencia GA8-220501096-AA1-EV02, integrando los módulos principales del sistema, documentando sus pruebas, configuraciones y entornos, y entregando los elementos técnicos necesarios para su despliegue y evaluación.

Repositorio GitHub: https://github.com/AnndresOsorio/sistema-integrado
