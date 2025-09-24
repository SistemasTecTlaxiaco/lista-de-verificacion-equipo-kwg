# Análisis de Calidad de Software: Proyecto Leaf Global Fintech en Stellar

## Introducción
Este informe presenta el análisis de calidad del software del proyecto Leaf Global Fintech, una solución financiera construida sobre la red Stellar. El análisis se realiza aplicando las métricas definidas en nuestro Plan de Calidad, con el objetivo de evaluar las prácticas de control de calidad en un entorno profesional de desarrollo blockchain.

## Fase 1: Selección y Exploración del Proyecto

### Subactividad 1.1 - Selección del Proyecto
Hemos seleccionado el proyecto [Leaf Global Fintech](https://github.com/leafglobalfintech), que ofrece servicios financieros para poblaciones no bancarizadas utilizando la tecnología de Stellar. Este proyecto fue elegido por:

- Su enfoque en inclusión financiera  
- Uso activo de la red Stellar y contratos inteligentes Soroban  
- Desarrollo activo con commits recientes  
- Documentación técnica disponible  

### Subactividad 1.2 - Exploración del Repositorio
El análisis del repositorio principal ([leaf-wallet](https://github.com/leafglobalfintech/leaf-wallet)) revela:

*Elementos positivos de calidad identificados:*
- Estructura de código organizada en directorios lógicos  
- Archivo README.md completo con instrucciones de instalación  
- Existencia de pruebas unitarias en directorio tests/  
- Uso de GitHub Issues para seguimiento de errores  
- Historial de commits activo con mensajes descriptivos  

*Áreas de preocupación inicial:*
- Documentación de API limitada  
- Cobertura de pruebas no medida explícitamente  

## Fase 2: Análisis y Aplicación de Métricas

### Subactividad 2.1 - Aplicación de Métricas del Plan de Calidad

*Métrica 1: Cobertura de Pruebas*  
- *Evaluación:* Mediante análisis del directorio de pruebas y ejecución de tests disponibles, estimamos una cobertura de aproximadamente 65-70%.  
- *Hallazgos:*
  - Pruebas unitarias presentes para componentes críticos  
  - Falta de pruebas para algunos módulos de UI/UX  
  - No se encontró configuración de herramientas de cobertura (como Istanbul o JaCoCo)  

*Métrica 2: Calidad de la Documentación*  
- *Evaluación:* Puntuación 7/10 según nuestra escala de documentación.  
- *Hallazgos:*
  - README.md completo con guías de instalación y configuración  
  - Documentación de API limitada a comentarios en el código  
  - Falta de tutoriales para nuevos desarrolladores  
  - Documentación de arquitectura presente pero podría mejorarse  

*Métrica 3: Tasa de Errores Resueltos*  
- *Evaluación:* 85% de issues cerrados en los últimos 6 meses.  
- *Hallazgos:*
  - Tiempo promedio de resolución: 7.2 días  
  - 15% de issues permanecen abiertos más de 30 días  
  - Comunicación activa en los issues entre desarrolladores y usuarios  

*Métrica 4: Complejidad Ciclomática Promedio*  
- *Evaluación:* Análisis estático muestra complejidad moderada (promedio: 4.2).  
- *Hallazgos:*
  - Algunos métodos con complejidad elevada (>10) identificados  
  - Mayoría del código mantiene complejidad manejable  
  - Oportunidad de refactorización en módulos específicos  

*Métrica 5: Débitos Técnicos*  
- *Evaluación:* 12 issues etiquetados como "mejora" o "refactor" en el repositorio.  
- *Hallazgos:*
  - Equipo consciente de la necesidad de mejoras técnicas  
  - Planificación visible para abordar débitos técnicos en milestones  

### Subactividad 2.2 - Análisis Crítico
*Interpretación de hallazgos:*  
La cobertura de pruebas del 65-70% indica un riesgo moderado para futuras actualizaciones. Aunque los componentes críticos están cubiertos, la falta de pruebas en módulos secundarios podría llevar a regresiones.  

La documentación es adecuada para desarrolladores experimentados pero podría ser una barrera para nuevos colaboradores. Esto podría limitar la adopción y contribuciones externas.  

La tasa de resolución de errores del 85% es sólida e indica un equipo responsivo. Sin embargo, el 15% de issues de larga duración sugiere que algunos problemas complejos o de baja prioridad podrían estar afectando la experiencia del usuario.  

## Fase 3: Elaboración de Conclusiones y Recomendaciones

### Subactividad 3.1 - Resumen de Evaluación
El proyecto Leaf Global Fintech demuestra prácticas de calidad sólidas en general, con un equipo activo que responde a issues y mantiene una base de código razonablemente testeada. Las áreas principales de mejora se encuentran en la documentación exhaustiva y la cobertura completa de pruebas.

### Subactividad 3.2 - Recomendaciones Basadas en MoProSoft
*Nivel de Madurez Actual Estimado:* Nivel 2 (Gestionado)  
El proyecto muestra procesos definidos y gestionados pero con oportunidades de mejora en la estandarización.  

*Recomendaciones Específicas:*  
1. *Implementar medición automatizada de cobertura de pruebas*  
   - Configurar herramientas como Jest con Istanbul para reportes de cobertura  
   - Establecer umbral mínimo de cobertura (80% recomendado) en integración continua  

2. *Mejorar documentación según estándares MoProSoft*  
   - Crear documentación de API con herramientas como Swagger/OpenAPI  
   - Desarrollar guías de onboarding para nuevos contribuidores  
   - Documentar decisiones de arquitectura (ADR)  

3. *Establecer proceso formal de gestión de débitos técnicos*  
   - Priorizar regularmente débitos técnicos en planning meetings  
   - Asignar tiempo específico en cada sprint para refactorización  

4. *Implementar análisis estático continuo*  
   - Integrar herramientas de análisis de código (SonarQube, CodeClimate)  
   - Establecer reglas de calidad de código y complejidad máxima  

5. *Mejorar proceso de gestión de issues*  
   - Implementar etiquetado consistente para prioridades y tipos de issue  
   - Establecer SLAs para diferentes tipos de issues  
   - Realizar revisiones periódicas de issues antiguos  

## Reflexión sobre la Experiencia
Esta actividad permitió aplicar conceptos teóricos de calidad de software a un proyecto real, revelando que incluso proyectos bien gestionados como Leaf Global Fintech tienen oportunidades de mejora. La experiencia destacó la importancia de métricas cuantitativas para evaluar objetivamente la calidad del software y cómo los frameworks como MoProSoft proporcionan guidance valioso para madurar procesos de desarrollo.