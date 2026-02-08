# Administración de Sistemas Linux - Iteración 2.0: CyberTech Solutions 🛡️

Esta es una versión optimizada de la infraestructura de **CyberTech Solutions**, enfocada en la seguridad avanzada, el cumplimiento del estándar FHS y la automatización de auditorías.

## 🏗️ 1. Infraestructura y Jerarquía (FHS)
Se ha migrado el proyecto al directorio `/opt` para seguir las mejores prácticas de software opcional. Se utiliza una estructura jerárquica para separar datos sensibles.

![Configuración de Estructura](01-creacion-estructura-opt.png)
*Despliegue de directorios departamentales mediante el uso de `mkdir -p`.*

## 👥 2. Gestión de Identidades (RBAC)
Implementación de un control de acceso basado en roles (RBAC) utilizando prefijos de grupo para una administración organizada.

![Configuración de Grupos](02-configuracion-grupos-ct.png)
*Creación de grupos técnicos con el prefijo `ct_` para estandarización.*

![Alta de Usuarios](03-alta-usuarios-gecos.png)
*Registro de empleados con metadatos descriptivos (GECOS).*

![Vinculación Grupal](04-vinculacion-usuarios-grupos.png)
*Asignación de privilegios departamentales mediante la gestión de grupos secundarios.*

## 🔐 3. Políticas de Acceso y Privacidad
Aplicación del **Principio de Menor Privilegio**. Cada departamento tiene aislamiento total de sus archivos.

![Propiedad de Carpetas](05-asignacion-dueños-carpetas.png)
*Transferencia de propiedad de directorios a sus respectivos grupos técnicos.*

![Permisos Restrictivos](06-seguridad-restrictiva-770.png)
*Configuración de bits de permisos 770 y 775 para el aislamiento de datos.*

![Estado de Permisos](07-verificacion-permisos-opt.png)
*Auditoría visual de la máscara de permisos final.*

## 🤖 4. Auditoría y Automatización
Configuración de un sistema de registro automático para monitorear la actividad de los usuarios en tiempo real.

![Log de Auditoría](08-configuracion-audit-log.png)
*Implementación de Cron Jobs para la recolección automática de logs en /var/log.*

## 🧪 5. Pruebas de Seguridad (Vectores de Acceso)
Validación de las reglas de negocio y restricciones de seguridad impuestas.

![Brecha Denegada](09-brecha-seguridad-denegada.png)
*Test A: Intento de acceso no autorizado entre departamentos (Resultado: Exitoso/Denegado).*

![Acceso Exitoso](10-acceso-exitoso-projects.png)
*Test B: Verificación de operatividad del usuario dentro de su entorno permitido.*

![Aislamiento Departamental](11-aislamiento-departamental.png)
*Test C: Validación de barreras de privacidad entre administración y desarrollo.*

## 🚫 6. Gestión de Bajas y Suspensión
Protocolo de seguridad para la inactivación de cuentas sin pérdida de integridad de datos.

![Bloqueo Administrativo](12-bloqueo-cuenta-administrador.png)
*Suspensión inmediata de credenciales desde la cuenta de administrador.*

![Suspensión Verificada](13-verificacion-suspension-acceso.png)
*Confirmación de inactividad de cuenta: acceso denegado post-bloqueo.*

