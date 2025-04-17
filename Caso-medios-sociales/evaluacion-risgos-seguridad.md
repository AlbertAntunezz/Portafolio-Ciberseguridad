# Informe de Evaluación de Riesgos de Seguridad
**Fecha:** 17 de abril de 2025  
**Analista:** Albert Antunez

---

## Parte 1: Seleccionar hasta tres herramientas y métodos de endurecimiento para implementar

**Herramientas/Métodos seleccionados:**  
1. **Autenticación Multifactor (MFA)**  
2. **Configuración y mantenimiento de reglas en el cortafuegos**  
3. **Políticas de contraseñas robustas**  

---

## Parte 2: Explicar las recomendaciones

### 1. **Autenticación Multifactor (MFA)**  
**Efectividad:**  
- Mitiga el riesgo de acceso no autorizado, incluso si las contraseñas son comprometidas (ejemplo: empleados compartiendo contraseñas o contraseñas predeterminadas).  
- Requiere una segunda forma de verificación (código SMS, app de autenticación, etc.), lo que dificulta a los atacantes el acceso a cuentas críticas como la base de datos administrativa.  

**Frecuencia de implementación:**  
- Configuración inicial única para todos los usuarios.  
- Mantenimiento continuo para actualizar métodos de autenticación y revisar accesos.  

---

### 2. **Configuración y mantenimiento de reglas en el cortafuegos**  
**Efectividad:**  
- Filtra el tráfico entrante/saliente no autorizado, bloqueando puertos y protocolos innecesarios.  
- Previene ataques como escaneo de puertos, accesos remotos no autorizados o tráfico malicioso hacia la red interna.  

**Frecuencia de implementación:**  
- **Inmediata:** Establecer reglas básicas (bloquear puertos no utilizados, permitir solo tráfico esencial).  
- **Periódica:** Auditorías mensuales para ajustar reglas según nuevas amenazas o cambios en la infraestructura.  

---

### 3. **Políticas de contraseñas robustas**  
**Efectividad:**  
- Elimina contraseñas predeterminadas o débiles (ejemplo: contraseña de administrador de la base de datos).  
- Exige complejidad (mínimo 12 caracteres, combinación de letras, números y símbolos) y evita reutilización.  

**Frecuencia de implementación:**  
- **Inicial:** Forzar el cambio de contraseñas predeterminadas y aplicar políticas.  
- **Periódica:** Revisiones trimestrales y notificaciones para actualizar contraseñas.  

---

### **Impacto en las vulnerabilidades identificadas:**  
| Vulnerabilidad                  | Solución aplicada               | Resultado esperado                          |
|----------------------------------|----------------------------------|---------------------------------------------|
| Contraseñas compartidas          | MFA + Políticas de contraseñas  | Acceso seguro incluso con contraseñas filtradas. |
| Contraseña predeterminada en BD  | Políticas de contraseñas        | Eliminación de credenciales vulnerables.     |
| Cortafuegos sin reglas           | Configuración de cortafuegos    | Bloqueo de tráfico malicioso y no autorizado. |
| Falta de MFA                     | Implementación de MFA           | Reducción del riesgo de acceso fraudulento.  |

---

**Conclusión:**  
La implementación de estas medidas aborda las vulnerabilidades críticas identificadas. La combinación de **MFA**, **cortafuegos configurados** y **políticas de contraseñas** crea capas de defensa que protegen contra accesos no autorizados y filtraciones futuras.
