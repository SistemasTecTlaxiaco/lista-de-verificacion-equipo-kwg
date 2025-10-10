# 🛡️ Matriz de Riesgos — Proyecto Stellar

## 1) Propósito
Identificar, evaluar y responder proactivamente a los riesgos técnicos, operativos y externos del proyecto en Stellar (Soroban, Horizon, CI/CD, documentación y cumplimiento).

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

> **Matriz Impacto vs Probabilidad (visual rápida)**
>
> |     | **I=5** | **I=4** | **I=3** | **I=2** | **I=1** |
> |-----|---------|---------|---------|---------|---------|
> | **P=5** | 🔴 | 🔴 | 🔴 | 🟡 | 🟡 |
> | **P=4** | 🔴 | 🔴 | 🟡 | 🟡 | 🟢 |
> | **P=3** | 🔴 | 🟡 | 🟡 | 🟢 | 🟢 |
> | **P=2** | 🟡 | 🟡 | 🟢 | 🟢 | 🟢 |
> | **P=1** | 🟡 | 🟢 | 🟢 | 🟢 | 🟢 |

## 4) Matriz de Riesgos (plantilla)
> Copia esta tabla y añade tantos renglones como necesites.

| ID | Riesgo | Tipo (Téc/Op/Ext) | Causa raíz | P (1–5) | I (1–5) | Score | Nivel | Indicadores tempranos | Dueño | Estrategia | Plan de respuesta (acciones) | Plan de contingencia | Estado |
|----|--------|-------------------|------------|---------|---------|-------|-------|------------------------|-------|-----------|------------------------------|----------------------|--------|
| R- |        |                   |            |         |         |       |       |                        |       |           |                              |                      | Abierto |

## 5) Ejemplos iniciales (puedes ajustarlos a tu proyecto)
| ID | Riesgo | Tipo | Causa raíz | P | I | Score | Nivel | Indicadores | Dueño | Estrategia | Plan de respuesta | Contingencia | Estado |
|----|--------|------|------------|---|---|-------|-------|------------|-------|-----------|-------------------|-------------|--------|
| R-01 | Bug crítico en contrato Soroban rompe flujos de préstamo | Téc | Curva de aprendizaje y tests insuficientes | 3 | 5 | 15 | 🔴 Alto | Falla en unit tests, revert de PR | Líder backend | **Mitigar** | Pruebas unitarias + integración en testnet, revisión 2 devs en PR, CI obligatorio | Congelar release, hotfix en rama `hotfix/*` | Abierto |
| R-02 | Exposición de claves/secretos en repo | Téc | Manejo manual de secretos | 2 | 5 | 10 | 🟡 Medio | Alerta de escaneo secreto | DevOps | **Evitar** | Secretos en variables de entorno + Vault, pre-commit secret scan | Revocar claves y rotación inmediata | Abierto |
| R-03 | Cambios en Horizon API afecten endpoints | Ext | Dependencia de terceros | 2 | 4 | 8 | 🟡 Medio | Errores 4xx/5xx nuevos | Backend | **Mitigar** | Cliente con *retry/backoff*, compat test semanal | Fallback a versión previa del SDK | Abierto |
| R-04 | Retraso por falta de mano de obra | Op | Subestimación de esfuerzo | 3 | 4 | 12 | 🟡 Medio | Burn-down con pendiente positiva | PM | **Mitigar** | Repriorizar MVP, dividir tareas, emparejar programadores | Mover alcance a siguiente sprint | Abierto |
| R-05 | Baja adopción de usuarios | Ext | Falta de comunicación | 2 | 4 | 8 | 🟡 Medio | Poco tráfico al README/landing | PO | **Mitigar** | Publicar en foros SCF/Discord, demo y guía simple | Encuestas + pivote de UX | Abierto |
| R-06 | Incumplir DoD (sin pruebas/linters) | Op | Presión por tiempos | 3 | 3 | 9 | 🟡 Medio | PRs sin checks verdes | QA | **Evitar** | Bloquear merge sin checks CI (lint+tests+coverage≥80%) | Hotfix con deuda técnica planificada | Abierto |
| R-07 | Caída del pipeline CI | Téc | Config inestable en Actions | 2 | 3 | 6 | 🟡 Medio | Builds fallan en cola | DevOps | **Transferir** | Cachés + runners externos confiables | Ejecutar manual en local con script | Abierto |
| R-08 | Cambio de reglas SCF o compliance | Ext | Políticas actualizadas | 1 | 4 | 4 | 🟢 Bajo | Anuncios SCF/ToS | PM | **Aceptar** | Monitor mensual y checklist | Ajuste de docs y términos | Abierto |
| R-09 | Falta de documentación para usuarios | Op | Priorización de código sobre docs | 3 | 3 | 9 | 🟡 Medio | Issues “how to” repetidos | Tech Writer | **Mitigar** | USER_GUIDE + FAQs + gifs | Mini videos de 60s | Abierto |
| R-10 | Conflictos de merge por Git Flow | Op | Branching no seguido | 3 | 3 | 9 | 🟡 Medio | PRs con diff enorme | PM | **Mitigar** | Políticas de ramas cortas, integrar a `develop` diario | Sesión de resolución de conflictos | Abierto |

## 6) Reglas de actualización
- Actualiza **P**/**I** cuando haya nueva evidencia.
- Cambia **Estado**: Abierto → En mitigación → Cerrado.
- Enlaza cada riesgo a su **Issue** correspondiente.

