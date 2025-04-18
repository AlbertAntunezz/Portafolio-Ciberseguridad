## Descripción del proyecto

Como profesional de seguridad en una organización, mi tarea fue auditar y corregir los permisos de archivos y directorios en el sistema Linux. El objetivo era garantizar que solo usuarios autorizados tuvieran acceso adecuado, eliminando privilegios innecesarios. Utilicé comandos como ls -la, chmod y chown para verificar y modificar permisos, asegurando la integridad del sistema según las políticas de la organización.

---

## Comprobar los detalles de archivos y directorios

**Comando utilizado:**

bash
ls -la /home/researcher2/projects

---

**Salida relevante (basada en "Current file permissions"):**

-rw-rw-rw- project_k.txt
-rw-r----- project_m.txt
-rw-rw-r-- project_r.txt
drwx--x--- drafts
-rw-rw---- .project_x.txt

---

## Describir la cadena de permisos
**Ejemplo:** -rw-rw-r-- (para project_r.txt):

**Primer carácter (-):** Indica que es un archivo regular.
**Siguientes 9 caracteres:**

**Usuario (rw-):** Lectura y escritura.
**Grupo (rw-):** Lectura y escritura.
**Otros (r--):** Solo lectura.

---

## Cambiar permisos de archivo
**Archivo problemático:** project_k.txt (permisos originales: -rw-rw-rw-).
**Comando:**

bash
chmod o-w project_k.txt
Resultado:
Nuevos permisos: -rw-rw-r--.

---

## Cambiar permisos de un archivo oculto

**Archivo:** .project_x.txt (permisos originales: -rw--w----).
**Requisito:** Usuario y grupo pueden leer; nadie puede escribir.
**Comando:**

bash
chmod u=r,g=r,o= .project_x.txt
Resultado:
Nuevos permisos: -r--r-----.

---

## Cambiar permisos de directorio

**Directorio:** drafts (permisos originales: drwx--x---).
**Requisito:** Solo researcher2 (usuario) debe acceder.
**Comando:**

bash
chmod go-rwx drafts
Resultado:
Nuevos permisos: drwx------.

---

## Resumen
En esta actividad, revisé y ajusté los permisos de archivos y directorios en Linux para cumplir con las políticas de seguridad. Mediante ls -la, identifiqué permisos incorrectos y usé chmod para restringir accesos no autorizados. Por ejemplo, eliminé escritura para "otros" en project_k.txt y aseguré que el directorio drafts solo sea accesible por su dueño. Estas acciones demuestran competencia en administración de permisos, clave para roles en ciberseguridad.
