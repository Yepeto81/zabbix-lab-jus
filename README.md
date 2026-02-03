# Zabbix Lab JUS

Este repositorio contiene un playbook de Ansible para instalar y configurar **Zabbix Server 6.0** en un entorno **Debian 10**.

## Características
- Instalación de Zabbix Server, Frontend y Agente.
- Configuración de PHP 7.3 con PHP-FPM y Apache (mod_proxy_fcgi).
- Configuración automática de la base de datos MariaDB (seguridad incluida).
- Bypass automático del asistente de configuración web (Wizard).
- Soporte para bases de datos externas mediante variables.
- Configuración de Firewalld.

## Requisitos
- Debian 10.
- Ansible instalado localmente.
- Usuario con permisos de sudo sin contraseña.

## Uso
1. Clonar el repositorio.
2. Editar `inventory.yml` con la IP de tu servidor.
3. Editar `vars.yml` con tus credenciales preferidas.
4. Ejecutar el playbook:
   ```bash
   ansible-playbook -i inventory.yml setup_zabbix.yml
   ```

## Autor
Desarrollado con la ayuda de Antigravity (Raquel).
