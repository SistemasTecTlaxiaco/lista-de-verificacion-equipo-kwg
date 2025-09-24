# Lista de Verificación de Auditoría - Leaf Global Fintech dApp

**Propósito:**  
Este documento sirve como guía para auditar el código y la documentación del proyecto. Garantiza que cada funcionalidad cumpla con los estándares de calidad del ecosistema Stellar, asegurando confiabilidad, seguridad y confianza de la comunidad y del comité de la SCF.

**Estado de la Auditoría:**  
- [ ] En Progreso  
- [ ] Completado  
- **Aprobado por el Revisor:** [Nombre del Revisor]

**Fecha de Auditoría:** [dd/mm/aaaa]  
**Revisores:** [Nombres de los revisores]  
**Observaciones Adicionales:** [Agregar comentarios si aplica]

---

## Sección 1: Auditoría de Código y Seguridad en la Red Stellar

| ID     | Criterio de Verificación                   | Descripción                                                                 | Estado      |
|--------|-------------------------------------------|-----------------------------------------------------------------------------|------------|
| C-1.1  | Manejo de Transacciones y Firmas           | Verificar que todas las transacciones financieras estén construidas y firmadas correctamente, incluyendo multifirma. | [ ] Pendiente |
| C-1.2  | Validación de Entradas (Frontend/API)     | Validar direcciones Stellar, montos, memos y datos de usuarios en frontend y backend. | [ ] Pendiente |
| C-1.3  | Uso de Claves Privadas                     | Asegurar que nunca se almacenen en servidores ni se expongan de forma insegura. | [ ] Pendiente |
| C-1.4  | Gestión de Cuentas y Trustlines           | Verificar creación de cuentas, trustlines, tarifas y límites de transacción. | [ ] Pendiente |
| C-1.5  | Integración con Soroban                    | Validar llamadas, eventos y datos en smart contracts, asegurando cumplimiento de requisitos financieros. | [ ] Pendiente |
| C-1.6  | Manejo de Errores de Horizon API           | Implementar manejo robusto de fallos y errores en llamadas a la API Horizon. | [ ] Pendiente |

---

## Sección 2: Auditoría de Documentación y Usabilidad

| ID     | Criterio de Verificación                  | Descripción                                                               | Estado      |
|--------|------------------------------------------|---------------------------------------------------------------------------|------------|
| D-2.1  | Guía de Configuración Completa            | Documentación con pasos claros para instalación, ejecución y configuración de cuentas de usuario. | [ ] Pendiente |
| D-2.2  | Diagramas de Arquitectura (SCF)          | Incluir diagramas de alto nivel mostrando la interacción dApp ↔ Stellar ↔ servicios externos. | [ ] Pendiente |
| D-2.3  | Documentación de la API (SEP)            | Documentar uso de endpoints y cumplimiento de protocolos SEP relevantes.   | [ ] Pendiente |
| D-2.4  | Manual de Usuario                         | Manual accesible para público no técnico, con ejemplos de uso de transacciones. | [ ] Pendiente |

---

## Sección 3: Cumplimiento y Ecosistema SCF

| ID     | Criterio de Verificación                  | Descripción                                                               | Estado      |
|--------|------------------------------------------|---------------------------------------------------------------------------|------------|
| E-3.1  | Licencia de Código Abierto                | Incluir licencia como MIT o Apache 2.0.                                   | [ ] Pendiente |
| E-3.2  | Política de Privacidad y Términos        | Redactar y publicar si se manejan datos personales o financieros.        | [ ] Pendiente |
| E-3.3  | Canales de Comunicación                   | Incluir Discord, Telegram u otros canales de soporte y atención a usuarios. | [ ] Pendiente |
| E-3.4  | Alineación con Objetivos SCF              | Destacar cómo el proyecto apoya inclusión financiera, pagos transfronterizos o educación financiera. | [ ] Pendiente |

---


