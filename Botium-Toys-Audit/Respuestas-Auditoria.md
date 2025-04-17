# Respuestas de Auditoría: Botium Toys  

### 📋 Checklist de Controles ###

| Control                                  | Implementado (Sí/No) |  
|------------------------------------------|-----------------------|  
| Least Privilege                          | No                    |  
| Disaster recovery plans                  | No                    |  
| Password policies                        | Sí (políticas débiles)|  
| Separation of duties                     | No                    |  
| Firewall                                 | Sí                    |  
| Intrusion detection system (IDS)         | No                    |  
| Backups                                  | No                    |  
| Antivirus software                       | Sí                    |  
| Manual monitoring (legacy systems)       | Sí (sin horario)      |  
| Encryption                               | No                    |  
| Password management system               | No                    |  
| Locks (oficinas/almacén)                 | Sí                    |  
| CCTV surveillance                        | Sí                    |  
| Fire detection/prevention                | Sí                    |  

--------------------------------------------------------------------

## 📜 Cumplimiento Normativo  

### PCI DSS ### 
| Mejor Práctica                           | Cumple (Sí/No) |  
|------------------------------------------|----------------|  
| Acceso autorizado a datos de tarjetas    | No             |  
| Ambiente seguro para datos de tarjetas   | No             |  
| Cifrado de datos                         | No             |  
| Gestión segura de contraseñas            | No             |  

### GDPR  ###
| Mejor Práctica                           | Cumple (Sí/No) |  
|------------------------------------------|----------------|  
| Privacidad de datos de clientes UE       | Parcialmente   |  
| Notificación de brechas en 72 horas      | Sí             |  
| Clasificación de datos                   | No             |  
| Documentación de políticas de privacidad | Sí             |  

### SOC  ###
| Mejor Práctica                           | Cumple (Sí/No) |  
|------------------------------------------|----------------|  
| Políticas de acceso                      | No             |  
| Confidencialidad de PII/SPII             | No             |  
| Integridad de datos                      | Sí             |  
| Disponibilidad de datos                  | Sí             |  

-------------------------------------------------------------

### 🚨 Recomendaciones Prioritarias  ###

1. Controles Críticos:  
   - Implementar cifrado para datos sensibles (tarjetas, PII).  
   - Crear planes de recuperación ante desastres y realizar backups periódicos.  
   - Instalar un sistema de detección de intrusos (IDS).  

2. Cumplimiento: 
   - Aplicar políticas de mínimo privilegio y separación de funciones.  
   - Actualizar políticas de contraseñas (mínimo 8 caracteres, símbolos).  
   - Adoptar un gestor centralizado de contraseñas.  

3. Mejoras Adicionales:  
   - Establecer un calendario para mantenimiento de sistemas heredados.  
   - Capacitar empleados en concienciación de seguridad.
