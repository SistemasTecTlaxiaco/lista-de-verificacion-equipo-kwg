# 🛡️ Matriz de Riesgos — Proyecto ShareCar

## 1) Propósito
Identificar, evaluar y responder proactivamente a los riesgos técnicos, operativos y externos del proyecto ShareCar (Soroban, Horizon, CI/CD, interfaz web, pagos y adopción de usuarios).

## 2) Proceso (cómo trabajaremos la actividad)
1. **Caza de villanos (Identificación):** lluvia de ideas por equipo (≥5 riesgos).  
2. **Ranking de villanos (Evaluación):** clasificar cada riesgo por **Probabilidad** y **Impacto** usando la escala de abajo.  
3. **Escudo de defensa (Respuesta):** definir estrategia: *Mitigar, Evitar, Transferir, Aceptar* con acciones concretas.  
4. **Seguimiento:** cada riesgo se crea como *Issue* con esta matriz como fuente de verdad.

## 3) Escalas y puntaje
- **Probabilidad (P):** 1 Muy baja, 2 Baja, 3 Media, 4 Alta, 5 Muy alta  
- **Impacto (I):** 1 Menor, 2 Bajo, 3 Moderado, 4 Alto, 5 Crítico  
- **Nivel de Riesgo:** `Score = P × I`  
  - 1–5 = 🟢 Bajo | 6–12 = 🟡 Medio | 15–25 = 🔴 Alto

> **Matriz Impacto vs Probabilidad**
>
> |     | **I=5** | **I=4** | **I=3** | **I=2** | **I=1** |
> |-----|---------|---------|---------|---------|---------|
> | **P=5** | 🔴 | 🔴 | 🔴 | 🟡 | 🟡 |
> | **P=4** | 🔴 | 🔴 | 🟡 | 🟡 | 🟢 |
> | **P=3** | 🔴 | 🟡 | 🟡 | 🟢 | 🟢 |
> | **P=2** | 🟡 | 🟡 | 🟢 | 🟢 | 🟢 |
> | **P=1** | 🟡 | 🟢 | 🟢 | 🟢 | 🟢 |

## 4) Matriz de Riesgos (plantilla)
| ID | Riesgo | Tipo (Téc/Op/Ext) | Causa raíz | P (1–5) | I (1–5) | Score | Nivel | Indicadores tempranos | Dueño | Estrategia | Plan de respuesta (acciones) | Plan de contingencia | Estado |
|----|--------|-------------------|------------|---------|---------|-------|-------|------------------------|-------|-----------|------------------------------|----------------------|--------|
| R- |        |                   |            |         |         |       |       |                        |       |           |                              |                      | Abierto |

## 5) Ejemplos iniciales (ShareCar)
| ID | Riesgo | Tipo | Causa raíz | P | I | Score | Nivel | Indicadores | Dueño | Estrategia | Plan de respuesta | Contingencia | Estado |
|----|--------|------|------------|---|---|-------|-------|------------|-------|-----------|-------------------|-------------|--------|
| R-01 | Bug crítico en contrato Soroban rompe pagos/reservas | Téc | Curva de aprendizaje y tests insuficientes | 3 | 5 | 15 | 🔴 Alto | Fallas en unit tests o revert de PR | Líder backend | **Mitigar** | Pruebas unitarias + integración en testnet, revisión 2 devs en PR, CI obligatorio | Congelar release, hotfix en rama `hotfix/*` | Abierto |
| R-02 | Exposición de claves/secretos de usuarios | Téc | Manejo manual de secretos | 2 | 5 | 10 | 🟡 Medio | Alertas de escaneo de secretos | DevOps | **Evitar** | Secretos en variables de entorno + Vault, pre-commit secret scan | Revocar claves y rotación inmediata | Abierto |
| R-03 | Cambios en Horizon API afecten endpoints | Ext | Dependencia de terceros | 2 | 4 | 8 | 🟡 Medio | Errores 4xx/5xx nuevos | Backend | **Mitigar** | Cliente con *retry/backoff*, tests de compatibilidad semanales | Fallback a versión previa del SDK | Abierto |
| R-04 | Retraso por falta de desarrolladores | Op | Subestimación de esfuerzo | 3 | 4 | 12 | 🟡 Medio | Burn-down con pendiente positiva | PM | **Mitigar** | Repriorizar MVP, dividir tareas, emparejar programadores | Mover alcance a siguiente sprint | Abierto |
| R-05 | Baja adopción de usuarios | Ext | Falta de comunicación o confianza | 3 | 4 | 12 | 🟡 Medio | Poco tráfico a landing / apps instaladas | PO | **Mitigar** | Publicar en foros estudiantiles, demo y guía simple | Encuestas + pivote de UX | Abierto |
| R-06 | Incumplir DoD (tests, linters, cobertura) | Op | Presión por tiempos | 3 | 3 | 9 | 🟡 Medio | PRs sin checks verdes | QA | **Evitar** | Bloquear merge sin checks CI (lint+tests+coverage≥80%) | Hotfix con deuda técnica planificada | Abierto |
| R-07 | Conflictos de merge por Git Flow | Op | Branching no seguido | 3 | 3 | 9 | 🟡 Medio | PRs con diff enorme | PM | **Mitigar** | Políticas de ramas cortas, integrar a `develop` diario | Sesión de resolución de conflictos | Abierto |
| R-08 | Fallas de pagos transfronterizos | Téc | Red Stellar congestionada o errores de smart contract | 2 | 5 | 10 | 🟡 Medio | Transacciones pendientes o revertidas | Backend | **Mitigar** | Retry automático, monitor de transacciones, testnet frecuente | Avisar usuarios, reintentos manuales | Abierto |
| R-09 | Falta de documentación para estudiantes | Op | Priorización de código sobre docs | 3 | 3 | 9 | 🟡 Medio | Issues “cómo usar” repetidos | Tech Writer | **Mitigar** | USER_GUIDE + FAQs + gifs | Mini videos tutoriales | Abierto |
| R-10 | Cambios en políticas universitarias o legales | Ext | Normativas actualizadas | 2 | 4 | 8 | 🟡 Medio | Comunicados de universidades o leyes | PM | **Aceptar** | Monitor mensual y checklist | Ajuste de funcionalidades y términos | Abierto |

## 6) Reglas de actualización
- Actualiza **P**/**I** cuando haya nueva evidencia.  
- Cambia **Estado**: Abierto → En mitigación → Cerrado.  
- Enlaza cada riesgo a su **Issue** correspondiente.
