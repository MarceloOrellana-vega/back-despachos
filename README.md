# 🚚 Innovatech Chile - API Backend Despachos

Este repositorio contiene el microservicio de gestión de Despachos para el proyecto **Innovatech Chile**, desarrollado bajo una arquitectura de tres capas y preparado para su despliegue automatizado en la nube (AWS).

## 🚀 Tecnologías Utilizadas
- **Lenguaje/Framework:** Java 17, Spring Boot
- **Gestor de dependencias:** Maven
- **Base de Datos:** MySQL
- **Contenedorización:** Docker & Docker Compose
- **CI/CD:** GitHub Actions

## 🏗️ Arquitectura y Seguridad
Este microservicio está diseñado para residir en una subred privada dentro de una instancia EC2 (`ec2-app`) en AWS.
Por razones de seguridad arquitectónica, **no posee acceso directo desde Internet**. Únicamente recibe peticiones provenientes del Security Group asociado al Frontend y se comunica con la capa de persistencia (Base de datos).

## 🗄️ Persistencia de Datos
La persistencia de este servicio está garantizada mediante el uso de **Volúmenes Docker**. Esto asegura que, ante cualquier reinicio, actualización o caída del contenedor de la base de datos, la información de los despachos se mantenga intacta en el host.

## 🛠️ Cómo ejecutar el proyecto localmente

1. Clona el repositorio:
   ```bash
   git clone [https://github.com/TuUsuario/back-despachos.git](https://github.com/TuUsuario/back-despachos