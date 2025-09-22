# Proceso de Verificación - StellarTracker dApp

Este documento describe cómo se llevará a cabo la verificación de la auditoría de código y documentación.

---

## Objetivo
Asegurar que StellarTracker cumpla con los estándares de calidad definidos en el Plan de Calidad, reduciendo riesgos de seguridad y mejorando la confiabilidad y mantenibilidad del software.

---

## Proceso
1. **Selección de responsables**  
   - Líder de Calidad coordina la auditoría.  
   - Un desarrollador diferente al autor del código revisa cada PR.  
   - Para cambios críticos (contratos, seguridad), se requieren **2 aprobaciones**.  

2. **Aplicación del checklist**  
   - Cada punto del archivo `AUDIT_CHECKLIST.md` debe revisarse y marcarse.  
   - Los hallazgos se registran en *issues* de GitHub.  

3. **Validación de herramientas automáticas**  
   - Linter y pruebas automáticas se ejecutan en cada commit/pull request.  
   - OWASP ZAP se corre en endpoints antes de release.  

4. **Revisión de documentación**  
   - El equipo valida que todos los archivos en `/docs` estén actualizados.  
   - Los manuales de usuario se revisan para claridad.  

---

## Roles
- **Líder de Calidad**: valida cumplimiento del proceso.  
- **Revisores**: aplican checklist y aprueban PRs.  
- **Autores**: corrigen hallazgos y mantienen la documentación.  

---

## Frecuencia
- Auditorías menores: en cada PR.  
- Auditorías completas: antes de cada release estable en `main`.  
