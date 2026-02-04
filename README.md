# Zabbix Lab JUS 🚀

Este repositorio contiene un framework de automatización con **Ansible Roles** diseñado para la implementación profesional y escalable de Zabbix Server en entornos multi-plataforma.

## Arquitectura Modular (Ansible Roles)
El proyecto ha sido refactorizado de un playbook monolítico a una estructura de roles, lo que permite una gestión desacoplada de cada servicio:

- **common**: Configuración base del sistema, locales y zona horaria.
- **apache**: Servidor web optimizado con soporte para PHP-FPM.
- **php**: Gestión dinámica de versiones (7.3 vs 8.4) y optimización de recursos.
- **mariadb**: Motor de base de datos con hardening de seguridad aplicado.
- **firewalld**: Gestión automatizada de reglas de tráfico.
- **zabbix_server**: Instalación del núcleo, gestión de esquemas y lógica de base de datos.
- **zabbix_agent**: Despliegue del agente de monitoreo local.
- **zabbix_frontend**: Interfaz web con bypass automático del asistente (Wizard).

## Soporte Multi-OS y Versiones
El playbook detecta automáticamente la distribución y aplica las configuraciones correspondientes:

| Distribución | Versión Zabbix | Versión PHP |
| :--- | :--- | :--- |
| **Debian 10 (Buster)** | Zabbix 6.0 LTS | PHP 7.3 |
| **Debian 13 (Trixie)** | Zabbix 7.0 LTS | PHP 8.4 |

## Características Principales
- **Carga Dinámica de Variables**: Los roles cargan configuraciones específicas según la versión del OS detectada.
- **Resiliencia de Base de Datos**: Detección automática de esquemas incompletos y restauración inteligente.
- **Bypass del Wizard**: Configuración automática del frontend para acceso inmediato.
- **Seguridad**: Hardening de MariaDB y gestión estricta de puertos vía Firewalld.

## Requisitos
- Host de control con Ansible.
- Debian 10 o Debian 13 en los servidores destino.
- Usuario con permisos de sudo sin contraseña.

## Guía de Uso Rápido
1. **Clonar el repositorio**:
   ```bash
   git clone https://github.com/Yepeto81/zabbix-lab-jus.git
   ```
2. **Configurar el Inventario**:
   Edita el archivo `inventory.yml` para definir tus hosts y variables globales (IPs, contraseñas, zona horaria).
3. **Ejecutar el Despliegue**:
   ```bash
   ansible-playbook -i inventory.yml setup_zabbix.yml
   ```

## Credenciales por Defecto
- **Usuario**: `Admin`
- **Contraseña**: `zabbix`

## Autor
Desarrollado con la ayuda de **Antigravity (Raquel)**.
