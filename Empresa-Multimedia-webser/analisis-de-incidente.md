# Análisis de Informe del Incidente según el Marco NIST CSF
**Fecha:** 17 de abril de 2025  
**Analista:** Albert Antunez

---

## **Resumen del Incidente**  
**Fecha del incidente:** 17 de abril de 2025
**Hora del incidente:** 14:00 - 16:00 (UTC)
**Tipo de ataque:** **Ataque DDoS (Denegación de Servicio Distribuido)** mediante avalancha de paquetes ICMP.  
**Impacto:**  
- Los servicios de red internos quedaron inaccesibles durante **2 horas**.  
- Interrupción de operaciones críticas de diseño web, gráfico y marketing.  

**Causa:**  
- **Firewall no configurado correctamente**, permitiendo tráfico ICMP malicioso.  
- **Direcciones IP falsificadas** en paquetes ICMP saturaron la red.

**Respuesta inicial:**  
- Bloqueo de paquetes ICMP entrantes.  
- Detención de servicios no críticos.  
- Restablecimiento de servicios críticos.  

---

## **Identificar (NIST CSF)**  
**Activos afectados:**  
- Servidores de red interna.  
- Servicios críticos de diseño y marketing.  
- Firewall y sistemas de monitoreo.  

**Vulnerabilidades identificadas:**  
- Configuración deficiente del firewall (ausencia de reglas para limitar tráfico ICMP).  
- Falta de monitoreo proactivo de tráfico anómalo.  
- Ausencia de autenticación multifactor (MFA) para accesos críticos.  

---

## **Proteger (NIST CSF)**  
**Medidas recomendadas:**  
1. **Configuración robusta del firewall:**  
   - Limitar la tasa de paquetes ICMP entrantes.  
   - Filtrar direcciones IP falsificadas.  
2. **Autenticación Multifactor (MFA):**  
   - Implementar MFA para accesos administrativos y críticos.  
3. **Actualizaciones de seguridad:**  
   - Parches regulares para sistemas operativos y software de red.  
4. **Políticas de contraseñas:**  
   - Exigir contraseñas complejas y cambios periódicos.  

---

## **Detectar (NIST CSF)**  
**Herramientas y métodos:**  
- **SIEM (Security Information and Event Management):**  
  - Correlacionar logs de firewall, IDS/IPS y servidores para detectar patrones anómalos.  
- **Sistemas IDS/IPS:**  
  - Alertar sobre tráfico ICMP masivo o direcciones IP sospechosas.  
- **Monitoreo en tiempo real:**  
  - Usar herramientas como **Wireshark** o **Nagios** para analizar tráfico.  

---

## **Responder (NIST CSF)**  
**Plan de respuesta:**  
1. **Contención:**  
   - Aislar segmentos de red afectados.  
   - Activar reglas de firewall predefinidas para bloquear tráfico malicioso.  
2. **Comunicación:**  
   - Notificar al equipo de seguridad, gerencia y clientes afectados.  
3. **Análisis forense:**  
   - Recolectar logs de firewall y servidores para identificar origen del ataque.  
4. **Mejoras post-incidente:**  
   - Revisar políticas de firewall y capacitar al equipo en respuesta a DDoS.  

---

## **Recuperar (NIST CSF)**  
**Acciones de recuperación:**  
1. **Restauración de servicios:**  
   - Priorizar servicios críticos usando backups validados.  
2. **Revisión de configuraciones:**  
   - Asegurar que el firewall esté configurado con reglas anti-DDoS.  
3. **Capacitación:**  
   - Entrenar al personal en identificación de tráfico sospechoso y uso de MFA.  
4. **Pruebas de estrés:**  
   - Simular ataques DDoS para validar la resistencia de la red.  

---

**Conclusión:**  
El informe cumple con el marco NIST CSF, abordando todas las funciones clave para gestionar y mitigar futuros incidentes.
