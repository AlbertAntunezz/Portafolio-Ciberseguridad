# Informe de Incidente: Ataque de Denegación de Servicio (DoS) - SYN Flood  
**Fecha:** 17 de abril de 2025  
**Analista:** Albert Antunez

---

## 🔍 **Sección 1: Identificación del tipo de ataque**

### **Tipo de Ataque**  
**Ataque SYN Flood** (Denegación de Servicio - DoS).

### **Evidencia en el Registro de Tráfico (Wireshark)**  
| No. | Tiempo      | Origen         | Destino    | Protocolo | Información del Paquete           |  
|-----|-------------|----------------|------------|-----------|-----------------------------------|  
| 52  | 3.390692    | 203.0.113.0    | 192.0.2.1  | TCP       | 54770→443 [SYN] Seq=0 Win=5792    |  
| 57  | 3.664863    | 203.0.113.0    | 192.0.2.1  | TCP       | 54770→443 [SYN] Seq=0 Win=5792    |  
| 122 | 20.167744   | 203.0.113.0    | 192.0.2.1  | TCP       | 54770→443 [SYN] Seq=0 Win=5792    |  

**Patrón Clave:**  
- **IP Atacante:** `203.0.113.0`.  
- **Puerto Objetivo:** `443` (HTTPS).  
- **Paquetes SYN Enviados:** Más de **200 solicitudes** en minutos.  

---

## ⚠️ **Sección 2:Impacto en la Red**
### **Síntomas Observados**  
1. **Saturación del Servidor:**  
   - El servidor (`192.0.2.1`) no pudo responder a conexiones legítimas.  
   - Errores registrados:  
     - `HTTP/1.1 504 Gateway Time-out` (Registro 77).  
     - `RST, ACK` para conexiones incompletas (Registro 73, 80).  

2. **Consecuencias:**  
   - **Disponibilidad:** Empleados no pudieron acceder a `/sales.html`.  
   - **Reputación:** Clientes recibieron errores de tiempo de espera.  
   - **Operaciones:** Interrupción temporal de ventas.  

---

## 🛠️ **Análisis Técnico**  
### **Mecánica del Ataque**  
1. **Three-Way Handshake Interrumpido:**  
   - **Paso 1 (SYN):** El atacante envía paquetes `SYN` falsificados.  
   - **Paso 2 (SYN-ACK):** El servidor reserva recursos y responde con `SYN-ACK`.  
   - **Paso 3 (ACK):** **No hay respuesta**, dejando conexiones en estado `SYN_RECEIVED`.  

2. **Saturación de Recursos:**  
   ```plaintext
   El servidor agotó su capacidad para manejar conexiones, priorizando solicitudes maliciosas sobre tráfico legítimo.

---

## 🛡️ **Recomendaciones de Mitigación**
### **Soluciones Inmediatas**

1. **SYN Cookies:** Activar en el servidor para evitar reservar recursos hasta confirmar conexiones.
2. **Firewall de Próxima Generación (NGFW):** Configurar reglas para bloquear tráfico de 203.0.113.0 y detectar patrones SYN anómalos.

### **Prevención a Largo Plazo**

1. **Rate Limiting:** Limitar conexiones SYN a 5/s por IP.
2. **Monitoreo con SIEM:** Alertas para tráfico inusual (ej: >100 SYN/s desde una IP).

---

## 📈 **Estado Actual y Próximos Pasos**

1. **Estado:** Servidor restaurado con bloqueo temporal de 203.0.113.0.
2. **Prioridad:** Implementar NGFW y SYN Cookies en 48 horas.
3. **Seguimiento:** Revisar logs diarios para detectar nuevos patrones.
