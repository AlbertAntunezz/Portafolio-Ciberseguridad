# Informe de Incidente de Seguridad
**Fecha:** 17 de abril de 2025  
**Analista:** Albert Antunez

## Sección 1: Identificar el protocolo de red implicado en el incidente

**Protocolo identificado:** **HTTP (Hypertext Transfer Protocol)**  
**Justificación:**  
- Los registros de tcpdump muestran múltiples solicitudes HTTP (ej. `HTTP: GET / HTTP/1.1`) hacia `yummyrecipesforme.com` y `greatrecipesforme.com`.  
- La descarga del malware y la redirección se realizaron mediante conexiones HTTP no cifradas (puerto 80).  
- Aunque se usó DNS para resolver direcciones IP, el ataque explotó HTTP para inyectar código JavaScript y distribuir malware.  

---

## Sección 2: Documentar el incidente

**Resumen del incidente:**  
- **Fecha y hora:** Detectado entre las **14:18 y 14:25** (según registros tcpdump).  
- **Ubicación:** Servidor web de `yummyrecipesforme.com` y sitio fraudulento `greatrecipesforme.com`.  
- **Descripción:**  
  - Un ex empleado ejecutó un **ataque de fuerza bruta** contra el panel administrativo, aprovechando una contraseña predeterminada.  
  - Tras acceder, modificó el código fuente para incrustar un script JavaScript que forzaba la descarga de un archivo malicioso.  
  - Al ejecutarse el archivo, los usuarios eran redirigidos a `greatrecipesforme.com`, infectando sus dispositivos con malware.  
- **Evidencia:**  
  - Registros tcpdump con solicitudes DNS/HTTP a las IPs `203.0.113.22` (legítima) y `192.0.2.172` (fraudulenta).  
  - Análisis del código fuente que confirmó la inyección de JavaScript.  
  - Reportes de clientes sobre redirecciones y lentitud en dispositivos.  

---

## Sección 3: Recomendar una solución para ataques de fuerza bruta

**Medida recomendada:** **Implementar Autenticación de Dos Factores (2FA)**  
**Justificación:**  
- **Efectividad:**  
  - Añade una capa adicional de seguridad (ej. código temporal enviado a un dispositivo móvil).  
  - Mitiga el riesgo de fuerza bruta: incluso con la contraseña correcta, el atacante no podría acceder sin el segundo factor.  
- **Acciones complementarias:**  
  - Limitar intentos de inicio de sesión.  
  - Exigir contraseñas complejas y actualizaciones periódicas.  

---

**Conclusión:**  
El incidente destaca la necesidad de reforzar la seguridad de cuentas administrativas. La implementación de **2FA**, junto con auditorías periódicas, reducirá significativamente el riesgo de accesos no autorizados.
