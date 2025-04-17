# Informe de Incidente de Ciberseguridad  (Actividad para Google Certificados)
**Fecha:** 17 de abril de 2025  
**Analista:** Albert Antunez  

---

## Parte 1: Resumen del problema en el registro tcpdump  

### Protocolos implicados  
- **DNS (UDP, puerto 53)**: Consultas desde el cliente (`192.51.100.15`) al servidor DNS (`203.0.113.2`) para resolver `yummyrecipesforme.com`.  
- **ICMP**: Respuestas con error *"puerto UDP 53 inalcanzable"*.  

### Hallazgos clave  
- **Puerto 53 inaccesible**: El servidor DNS no responde a solicitudes UDP en el puerto 53.  
- **Errores recurrentes**: Múltiples intentos fallidos seguidos de mensajes ICMP (3 intentos registrados).  

### Problema principal  
El servicio DNS en `203.0.113.2` no está operativo o está bloqueado, impidiendo la resolución del dominio.  

---

## Parte 2: Análisis y causa probable  

### Cronología del incidente  
- **Primer reporte**: 13:24:32 (según marcas de tiempo en tcpdump).  
- **Síntomas reportados**:  
  - Usuarios no podían acceder a `www.yummyrecipesforme.com`.  
  - Mensaje de error: *"Puerto de destino inalcanzable"*.  

### Acciones tomadas  
1. **Captura de tráfico**: Uso de `tcpdump` para analizar solicitudes DNS.  
2. **Identificación de patrones**:  
   - Consultas UDP al puerto 53 sin respuesta válida.  
   - Respuestas ICMP indicando inaccesibilidad del puerto.  

### Causa raíz probable  
- **Configuración incorrecta del servidor DNS**: Servicio no activo o mal configurado.  
- **Firewall restrictivo**: Bloqueo del puerto 53 UDP en el servidor o red.  

### Próximos pasos  
1. **Verificar estado del servicio DNS**:  
   - Reiniciar servicio en `203.0.113.2`.  
   - Validar configuración de zona DNS.  
2. **Revisar políticas de firewall**:  
   - Asegurar que el puerto 53 UDP esté permitido.  
3. **Monitoreo post-corrección**:  
   - Realizar pruebas de conectividad y resolución DNS.  

---

## Conclusión  
El incidente se originó por la inaccesibilidad del puerto 53 UDP en el servidor DNS, interrumpiendo la resolución del dominio. Se recomienda implementar monitoreo continuo para evitar recurrencias.  

**Prioridad:** 🔴 Alta (impacto en disponibilidad del sitio web).  
**Estado:** 🕵️ En investigación.
