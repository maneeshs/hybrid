---

copyright:
  years: 2017
lastupdated: "2017-05-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}


# Detalles de informe por tipo

## Inicios de sesión de cortafuegos
{: #firewalllogins}

Informa de sucesos relacionados con el inicio de sesión del administrador en los dispositivos de cortafuegos Vyatta.

### Campos de datos 

<dl>
<dt>Hora de origen de registro</dt>
<dd>Fecha en que se produjo el suceso.</dd>
<dt>Nombre del suceso</dt>
<dd>Tipo de suceso (usuario que no puede iniciar sesión a través de SSH - contraseña incorrecta, anomalía en la autenticación, cierre de sesión, contraseña aceptada para el usuario, sesión abierta para el usuario). </dd>
<dt>Categoría de nivel bajo</dt>
<dd>Detalles del suceso (anomalía de inicio de sesión SSH, sesión cerrada, inicio de sesión en host satisfactorio, sesión abierta). </dd>
<dt>Nombre de usuario</dt> 
<dd>Credenciales (nombre de usuario) del usuario que inició la sesión. </dd>
<dt>IP de origen</dt>
<dd>Dirección IP desde la que el usuario inicia la sesión.
<dt>IP de destino</dt>
<dd>Destino de la sesión. </dd>
<dt>Origen de registro</dt>
<dd>Origen del suceso (el nombre de host del cortafuegos que generó el suceso). </dd>
</dl>

## Denegaciones de cortafuegos
{: #firewalldenies}

Informa de sucesos generados por los dispositivos cortafuegos Vyatta cuando se deniega una solicitud de acceso debido a las reglas vigentes del cortafuegos. 
  
### Campos de datos 

<dl>
<dt>Hora de origen de registro</dt>
<dd>Fecha y hora a la que se produjo el suceso.</dd>
<dt>Nombre del suceso</dt>
<dd>Tipo de suceso (usuario que no puede iniciar sesión a través de SSH - contraseña incorrecta, anomalía en la autenticación, cierre de sesión, contraseña aceptada para el usuario, sesión abierta para el usuario). </dd>
<dt>Categoría de nivel bajo</dt>
<dd>Detalles del suceso de denegación del cortafuegos </dd>
<dt>IP de origen</dt> 
<dd>Dirección IP de origen desde donde la conexión de red y/o ataque se inicia.</dd>
<dt>Puerto de origen </dt>
<dd>Puerto de destino de protocolo.
<dt>IP de destino</dt>
<dd>Destino de la sesión. </dd>
<dt>Puerto de destino </dt>
<dd>Puerto de destino de protocolo.
</dd>
<dt>Protocolo
</dt>
<dd>Protocolo de comunicación (tcp/udp).
<dt>Origen de registro</dt>
<dd>Origen del suceso (nombre de host del cortafuegos que generó el suceso). </dd>
<dt>Número de sucesos</dt>
<dd>Número de sucesos de dicho tipo. </dd>
</dl>

## Inicios de sesión de sistema operativo
{: #oslogin}

Informa de sucesos generados por el sistema operativo cuando un administrador inicia una sesión SSH en un sistema Bluemix. 

### Campos de datos 

<dl>
<dt>Hora de origen de registro</dt>
<dd>Fecha en que se produjo el suceso.</dd>
<dt>Nombre del suceso</dt>
<dd>Tipo de suceso (autenticación de espacio de usuarios, anomalía de autenticación de espacio de usuarios)</dd>
<dt>Nombre de usuario</dt> 
<dd>Nombre del usuario que ha iniciado el proceso de autenticación.</dd>
<dt>Dirección de origen</dt>
<dd>Dirección IP desde la que el usuario inicia la sesión.
<dt>IP de destino</dt>
<dd>Destino de la sesión. </dd>
<dt>Origen de registro</dt>
<dd>Origen del suceso (el nombre de host del servidor desde el que se generó el suceso). </dd>
</dl>

## Inicios de sesión de servidor 
{: #loginserverlogins}

Informa de los sucesos que el componente de inicio de sesión de la plataforma Bluemix genera cuando un usuario de dicha plataforma inicia una sesión desde la línea de mandatos, desde las API REST o desde la consola de Bluemix. 

### Campos de datos 

<dl>
<dt>Hora de origen de registro</dt>
<dd>Fecha en la que se ha producido el suceso.</dd>
<dt>Nombre del suceso</dt>
<dd>Tipo de suceso (autenticación de espacio de usuarios, anomalía de autenticación de espacio de usuarios)</dd>
<dt>Usuario</dt> 
<dd>ID del usuario que ha iniciado el proceso de autenticación.</dd>
<dt>Bluemix_Platform_Component</dt>
<dd>Componente que generó el suceso (login_server).
<dt>Tipo de mensaje </dt>
<dd>Tipo de operación (inicio de sesión, fin de sesión). </dd>
<dt>Estado</dt>
<dd>Resultado de la operación (éxito/anomalía). </dd>
<dt>Origen de registro</dt>
<dd>Origen del suceso. </dd>
</dl>

## Administración de bases de datos 
{: #dbadmin}

Informa de sucesos relacionados con las operaciones realizadas por un administrador en las bases de datos internas de Bluemix. 

### Campos de datos 

<dl>
<dt>Hora de origen de registro</dt>
<dd>Fecha en la que se ha producido el suceso.</dd>
<dt>Event_Type</dt>
<dd>Tipo de suceso (SECURITY_RUNTIME).
<dt>Usuario</dt> 
<dd>Nombre del usuario que realizó la operación. A continuación se indican los usuarios definidos para la base de datos.
<ul>
<li>UAADB: vcap, root, backup_user.
<li>CCDB: vcap, ccadmin, backup_user.
<li>La utilización fuera de los anteriores precisará de la investigación sobre quién realizó la operación. Esto se puede hacer utilizando el Informe de seguridad de administración del sistema operativo y el Informe de seguridad de inicio de sesión de sistema operativo.
</ul>
</dd>
<dt>Origen</dt> 
<dd>Dirección IP desde la que el usuario inicia el mandato. Los valores esperados son los siguientes:
<ul>
<li>UAADB – Máquinas virtuales uaa y la máquina virtual nfs_WAL_server.
<li>CCDB – Máquinas virtuales nsf_WAL_server, api_worker, clock_global y cloud_controller_ng.
</ul>
</dd>
<dt>DB_Statement</dt>
<dd>Tipo de operación (todas las sentencias de definición de datos como, por ejemplo, sentencias CREATE, ALTER y DROP, además de sentencias de modificación de datos como, por ejemplo, INSERT, UPDATE, DELETE, TRUNCATE y COPY FROM)</dd>
<dt>DB_Name</dt>
<dd>Nombre de la base de datos en la que se ha realizado la operación </dd>
</dl>

## Gestión de usuarios de la consola de administración
{: #acusermgmt}

Informa de actividades de gestión de usuarios realizada en la consola de administración de Bluemix. 

### Campos de datos 

<dl>
<dt>Hora de origen de registro</dt>
<dd>Fecha en la que se ha producido el suceso.</dd>
<dt>Event_Type</dt>
<dd>Tipo de suceso (SECURITY_RUNTIME).
<ul>
<li>SECURITY_MGMT_REGISTRY: Añadir usuario [ID usuario]
<li>SECURITY_MGMT_REGISTRY: Suprimir usuario [ID usuario]
<li>SECURITY_AUTHN_CREDS_MODIFY: Añadir permisos [permisos] a usuarios [ID usuario].
<li>SECURITY_AUTHN_CREDS_MODIFY: Eliminar permisos [permisos] de usuarios [ID usuario].
<li>SECURITY_MGMT_CONFIG: Crear organización [nombre].
<li>SECURITY_MGMT_CONFIG: Cambiar gestores de la organización, [id].
<li>SECURITY_MGMT_CONFIG: Renombrar id de organización [id] a un nuevo nombre [nombre].
<li>SECURITY_MGMT_CONFIG: Suprimir id de organización [id].
<li>SECURITY_MGMT_CONFIG: Actualizar cuota para el id de organización [id] a la cuota [plan_cuota].
</ul>
</dd>
<dt>Usuario</dt> 
<dd>Usuario que ha iniciado la operación (ID LDAP).
<dt>Mensaje</dt> 
<dd>Mandato ejecutado.<ul>
<li>Añadir usuario [ID usuario]: Añade un usuario con el ID especificado.
<li>Suprimir usuario [ID usuario]: Suprime un usuario con el ID especificado.
<li>Añadir permiso [permisos] a los usuarios [ID usuario]: Añade permisos a los usuarios especificados. Los permisos pueden incluir:
ops.admin, ops.login, ops.reports.read, ops.reports.write, ops.catalog.read, ops.catalog.write, ops.users.read y ops.user.write.
<li>Eliminar permisos [permisos] de los usuarios [ID usuario]: Eliminar permiso - Elimina permisos de los usuarios especificados. Los permisos incluyen: ops.admin, ops.login, ops.reports.read, ops.reports.write, ops.catalog.read, ops.catalog.write, ops.users.read y ops.users.write.
<li>Crear organización [nombre]: Crea una organización con el nombre especificado.
<li>Cambiar gestores de organización [id]: Configura a los gestores de una organización para que sean los usuarios especificados.
<li>Renombrar id de organización [id] por un nuevo nombre [nombre]: Renombra la organización especificada.
<li>Suprimir usuario [ID usuario]: Suprime un usuario con el ID especificado.
<li>Suprimir id de organización [id]: Suprime la organización especificada.
<li>Actualizar cuota de la organización [id] [Plancuota]: Actualiza el plan de cuota para la organización especificada. Los planes incluyen: q2GB, q4GB, q8GB, q16GB, q32GB, q64GB, q128GB, q256GB, q512GB.
</ul>
</dd>
<dt>Origen de registro</dt>
<dd>Origen del suceso (la dirección IP/nombre de host del servidor que generó el suceso)</dd>
</dl>

## Gestión del catálogo
{: #catalogmgmt}

Informa de sucesos relacionados con las actividades de gestión de catálogos de servicios realizadas en la consola de administración de Bluemix.  

### Campos de datos 

<dl>
<dt>Hora de origen de registro</dt>
<dd>Fecha en la que se ha producido el suceso.</dd>
<dt>SECURITY_MGMT_CONFIG</dt>
<dd>Registrar plantilla [id]. Habilita un contenedor de modelo o un tiempo de ejecución con el ID especificado para que aparezca como una opción para todos los usuarios en el catálogo. </dd>
<dd>Anular registro de plantilla [id]. Hace que un contenedor de modelo o un tiempo de ejecución dejen de aparecer como una opción para todos los usuarios en el catálogo. </dd>
<dd>Actualizar plan de servicio [id] a público = [ público ] con visibilidades = [ id ]. Actualiza la visibilidad del plan de servicio especificado. 
Si público se establece en verdadero, los planes son visibles en todas las organizaciones. Si público se establece en falso, se debe proporcionar un conjunto de identificadores de organización para indicar las organizaciones que podrán ver este plan de servicio. </dd>
<dd>Añadir intermediario de servicio [nombre]. Añade un intermediario de servicio con el nombre especificado. </dd>
<dd>Suprimir intermediario de servicio [nombre]. Suprime el intermediario de servicio con el nombre especificado. </dd>
<dd>Actualizar paquete de compilación [id]. Actualiza el paquete de compilación solicitado con el id especificado. </dd>
<dt>Origen de registro</dt>
<dd>Origen del suceso (la dirección IP/nombre de host del servidor que generó el suceso)</dd>
</dl>

## Gestión de informes de seguridad
{: #securityreportsmgmt}

Informa de sucesos relacionados con las actividades de gestión de informes de seguridad realizadas en la consola de administración. 

### Campos de datos 

<dl>
<dt>Hora de origen de registro</dt>
<dd>Fecha en la que se ha producido el suceso.</dd>
<dd>Tipo de suceso (SECURITY_RUNTIME).
<ul>
<li>SECURITY_DATA_SYNC: Cargar informe [nombre] de categoría [nombre] con fecha [fecha].
Suprimir informe con ID[id]
<li>SECURITY_RESOURCE_ACCESS: Descargar informe [nombre].
</ul>
</dd>
<dt>Usuario</dt> 
<dd>Usuario que inició la operación.
<dt>Mensaje</dt> 
<dd>Mandato ejecutado.<ul>
<li>Cargar informe [nombre] de categoría [nombre] con fecha [fecha]: Cargar - Carga un informe con el nombre de archivo especificado y la fecha en la categoría especificada.
<li>Suprimir informe con ID [id]: Suprimir - Suprime un informe con el id especificado.
<li>Descargar informe [nombre]: Descargar - Descargar un informe con el nombre especificado.
</ul>
</dd>
<dt>Origen de registro</dt>
<dd>Origen del suceso (la dirección IP/nombre de host del servidor que generó el suceso)</dd>
</dl>

## Revisiones de acceso
{: #accessreviews}

Informa de solicitudes de accesos privilegiados del entorno de Bluemix, y su proceso por parte de los administradores de Bluemix.  

### Campos de datos 

<dl>
<dt>Action_Name</dt>
<dd>Indica la solicitud de un usuario para ser parte de un grupo, para renombrar el id de usuario, para revocar en caso de rechazo, para ser eliminado de un grupo (Añadir, Renombrar, Revocar, Suprimir). </dd>
<dt>Estado</dt>
<dd>Este campo indica el estado de la solicitud. El aprobador acepta o rechaza la solicitud. 
La solicitud está a la espera para su aprobación. El usuario cancela la solicitud (Aceptada, Rechazada, Pendiente, Cancelada). </dd>
<dt>Id_User</dt>
<dd>Nombre de usuario</dd>
<dt>User_name</dt> 
<dd>Usuario que realiza la solicitud.</dd>
<dt>Manager_Approval</dt>
<dd>Fecha en la que el gestor aprobó la solicitud
<dt>Access_Approval</dt>
<dd>Fecha en la que el gestor de grupos aprobó la solicitud.
</dd>
</dl>

## Gestión de claves
{: #keymgmt}

Informa de operaciones de gestión de certificados de claves. 

### Campos de datos 

<dl>
<dt>Hora de origen de registro</dt>
<dd>Fecha en la que se ha producido el suceso.</dd>
<dt>Event_Name</dt>
<dd>Tipo de suceso (Creación de clave, Creación de certificado, Supresión de certificado). </dd>
<dt>Nombre clave/certificado</dt>
<dd>Nombre de certificado o nombre de clave utilizado. </dd>
<dt>Key_Mgmt_Message</dt> 
<dd>Mandato ejecutado (creación de clave "nombre de clave", creación de certificado "nombre de certificado", supresión de configuración de certificado "nombre certificado"). </dd>
<dt>IP de destino</dt>
<dd>Destino de la sesión.
<dt>Origen de registro</dt>
<dd>Origen del suceso. </dd>
</dl>

## Notificaciones del sistema
{: #systemnotifications}

Informa de sucesos relacionados con la configuración de suscripciones de notificaciones o ventanas de despliegue de actualización de software. 

### Campos de datos 

<dl>
<dt>Hora de origen de registro</dt>
<dd>Fecha en la que se ha producido el suceso.</dd>
<dt>Event_Type</dt>
<dd>Tipo de suceso (SECURITY_RUNTIME).
<ul>
<li> SECURITY_MGMT_CONFIG: Crear ventana [id].
<li> SECURITY_MGMT_CONFIG: Actualizar ventana [id].
<li> SECURITY_MGMT_CONFIG: Suprimir ventana [id].
<li> SECURITY_MGMT_CONFIG: Crear suscripción [id].
<li> SECURITY_MGMT_CONFIG: Actualizar suscripción [id].
<li> SECURITY_MGMT_CONFIG: Suprimir suscripción [id].
<li> SECURITY_MGMT_CONFIG: Crear suscripción [id].
</ul>
</dd>
<dt>Usuario</dt> 
<dd>Usuario que inició la operación
<dt>Mensaje</dt>
<dd>Mandato ejecutado.<ul>
<li>Crear ventana [id]: Creates "Creando" las ventanas de actualización para un entorno. Las ventanas de actualización son las ventanas temporales preferidas y de indisponibilidad para los despliegues. Los clientes indican cuando permiten/cuando no permiten despliegues no disruptivos sin la necesidad de aprobarlos y planificarlos.
<li>Ventana de actualización [id]: Actualiza una ventana de actualización de mantenimiento. Este suceso se genera cuando un usuario está actualizando las ventanas de actualización de mantenimiento para un entorno.
<li>SECURITY_MGMT_CONFIG: Suprimir ventana de actualización. Este suceso se genera cuando el usuario delega las ventanas de actualización de un entorno.
<li>Crear suscripción [id]: Crea una suscripción de sucesos. Los registros de auditoría de suscripción de sucesos se generan cuando un usuario crea una suscripción para sucesos de incidencia o actualización. Esto le permitirá ser notificado cuando algo ocurra en el sistema.
<li>Actualizar suscripción [id]: Actualiza una suscripción de sucesos. El suceso se genera cuando un usuario actualiza una suscripción para sucesos de incidencias o actualización.
<li>Suprimir suscripción [id]: Suprimir una suscripción de sucesos. Este suceso se genera cuando un usuario suprime una suscripción para sucesos de incidencia o actualización.
<li>Crear respuesta de tema [id]: Respuesta a un tema. El registro de auditoría de respuesta de tema se genera cuando el cliente aprueba y planifica una actualización disruptiva.
</ul>
</dd>
<dt>Origen de registro</dt>
<dd>Origen del suceso (la dirección IP/nombre de host del servidor que generó el suceso). </dd>
</dl>

## Administración de la plataforma Bluemix
{: #platformadmin}

Informa de sucesos relacionados con la plataforma Bluemix utilizando la línea de mandatos, las API REST o la interfaz de usuario de Bluemix. 

### Campos de datos 

<dl>
<dt>Hora de origen de registro</dt>
<dd>Fecha en que se produjo el suceso.</dd>
<dt>Event_Type</dt>
<dd>Tipo de suceso (SECURITY_RUNTIME).
<ul>
<li>SECURITY_AUTH_CREDS_MODIFY: Sucesos relacionados con la modificación de credenciales para una identidad de usuario dada.
<li>SECURITY_MGMT_RESOURCE: Sucesos de gestión de recursos como, por ejemplo, creación, supresión y cambios a los atributos de un recurso.
<li>SECURITY_MGMT_POLICY: Sucesos relacionados con la gestión de políticas de seguridad como, por ejemplo, la creación de listas de control de acceso.
<li>SECURITY_RUNTIME: Sucesos de tiempo de ejecución como, por ejemplo, los de inicio y detención de servidores de seguridad.
<li>SECURITY_RESOURCE_ACCESS: Sucesos que registran todos los accesos a un recurso. Por ejemplo, todos los accesos a un archivo, todas las solicitudes/respuestas HTTP a una página web dada o todos los accesos a una tabla de base de datos crítica.
</ul>
</dd>
<dt>Usuario</dt> 
<dd>Usuario que inició la operación.
<dt>Destino</dt> 
<dd>Detalles de la operación ejecutada como, por ejemplo, el id de la entidad y los resultados de la operación. Ejemplos:
<ul>
<li>UserCreatedEvent ('["user_id=ca3a811f-1778-4103-9553-537788ed4c4e","username=equaranta"]’). El usuario se creó con (username=equaranta e id = ca3a811f-1778-4103-9553-537788ed4c4e).
<li>GroupModifiedEvent ('{" "group_name":"ops.reports.read","members":["0625ff9a- 8a59-4cca-a80a-8e3b51f3dd21","5005f0f8-e090-4cabb51d- 2ceee70acf0e"}'). Se modificó el grupo denominado ops.reports.read, con pertenencia resultante (id 0625ff9a- 8a59-4ccaa80a- 8e3b51f3dd21","5005f0f8- e090-4cab-b51d- 2ceee70acf0e).
<li>UserDeletedEvent ('["UserDeletedEvent ('["user_id=5cd5f412-4bbb-4c44-b44b- 713a5bc6144d","username=818811853"]'):"]'. 
Se suprimió el usuario con el id value=5cd5f412-4bbb- 4c44-b44b-713a5bc6144.
</ul>
</dd>
<dt>Mensaje</dt>
<dd>Entidad en la que se ejecutó la operación (serie de mensaje) o el código de retorno http estándar de la operación (valor numérico). </dd>
<dt>Bluemix_Platform_Component</dt>
<dd>Nombre del componente. </dd>
<dt>Origen de registro</dt>
<dd>Dirección IP/nombre de host del origen del suceso. </dd>
<dt>Origen</dt>
<dd>Origen del suceso (por ejemplo, la dirección IP). </dd>
<dt>Datos</dt>
<dd>Detalles adicionales. </dd>
</dl>

## Administración del sistema operativo
{: #osadmin}

Informa de sucesos que Bluemix ha generado y que podrían ayudarle a diagnosticar anomalías (por ejemplo, error en un despliegue de un agente Bosh o un servicio que no se inicia). 

### Campos de datos 

<dl>
<dt>Hora de origen de registro</dt>
<dd>Fecha en la que se ha producido el suceso.</dd>
<dt>Event_Name</dt>
<dd>Tipo de suceso (Creación de clave, Creación de certificado, Supresión de certificado). </dd>
<dt>BMX_key</dt>
<dd>Tipo de operación (BMX_executed_command, BMX_access_unauthorized, BMX_unsuccessful_delete, BMX_sudoers_folder, BMX_Identity_shadow, BMX_extended_attribute, BMX_sudoers).</dd>
<dt>auid</dt> 
<dd>ID de usuario de origen que ha iniciado una sesión (por ejemplo, auid=0 es root, auid=1000 es vcap, auid= 55044 es un usuario ldap). </dd>
<dt>uid</dt>
<dd>ID de usuario de destino con el que se ejecuta el mandato (por ejemplo, auid=55044 ha iniciado una sesión y realiza un mandato “sudo su” (root) -> uid=0, antes de ejecutar el mandato).
<dt>exe_key</dt>
<dd>Mandato ejecutado. </dd>
<dt>IP de origen</dt>
<dd>Dirección IP desde la que el usuario inicia el mandato. </dd>
<dt>Origen de registro</dt>
<dd>Origen del suceso. </dd>
</dl>
