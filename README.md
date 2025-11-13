# 🍕 Pizza Hut Colombia - Test Automation Suite

Suite de automatización de pruebas **LIMPIA Y EJECUTABLE** con Playwright para https://www.pizzahut.com.co/

## ✨ Características

✅ **12 tests ejecutables** - Tests reales, sin flakiness  
✅ **Sin anti-patterns** - Código limpio y profesional  
✅ **Cero waitForTimeout** - Solo auto-waiting de Playwright  
✅ **Tests determinísticos** - Resultados consistentes  
✅ **Selectores robustos** - Usando roles ARIA y data-testid  
✅ **Bien documentado** - Cada test tiene propósito claro  

## 🎯 Suite de Tests

### 📦 Test Suite Overview

| ID | Nombre | Categoría | Prioridad |
|---|---|---|---|
| **T001** | Carga de página principal | Funcionalidad | 🔴 Crítico |
| **T002** | Navegación y visualización de productos | Funcionalidad | 🔴 Crítico |
| **T003** | Interactividad de productos | Funcionalidad | 🟡 Alto |
| **T004** | Búsqueda de productos | Búsqueda | 🟡 Alto |
| **T005** | Búsqueda con término inválido | Búsqueda | 🟢 Medio |
| **T006** | Validación de formularios | Validación | 🟡 Alto |
| **T007** | Manejo de rutas inválidas | Errores | 🟢 Medio |
| **T008** | Responsive design (4 resoluciones) | UX | 🟡 Alto |
| **T009** | Seguridad HTTPS | Seguridad | 🔴 Crítico |
| **T010** | Performance de carga | Performance | 🟡 Alto |
| **T011** | Navegación principal | Navegación | 🟡 Alto |
| **T012** | Footer y enlaces | Estructura | 🟢 Medio |

### 📋 Descripción Detallada de Tests

#### **T001: Carga de Página Principal** 🔴
Valida que la página principal cargue correctamente:
- ✓ Título correcto
- ✓ URL con HTTPS
- ✓ Navegación visible
- ✓ Logo cargado
- ✓ CTA principal disponible
- ✓ Monitoreo de errores de consola

#### **T002: Navegación y Visualización de Productos** 🔴
Valida el acceso al menú de productos:
- ✓ Navegación exitosa al menú
- ✓ Productos visibles en la página
- ✓ Información completa (nombre, precio, botón)
- ✓ Al menos 1 producto disponible

#### **T003: Interactividad de Productos** 🟡
Verifica que los productos tengan botones funcionales:
- ✓ Botones visibles y habilitados
- ✓ Botones tienen texto descriptivo
- ✓ Productos son interactivos

#### **T004 & T005: Funcionalidad de Búsqueda** 🟡
Valida el sistema de búsqueda:
- ✓ Búsqueda retorna resultados o mensaje apropiado
- ✓ Términos inválidos se manejan correctamente
- ✓ No crashea con búsquedas inválidas

#### **T006: Validación de Formularios** 🟡
Verifica validación de campos:
- ✓ Emails inválidos son detectados
- ✓ Emails válidos son aceptados
- ✓ Validación HTML5 funciona

#### **T007: Manejo de Rutas Inválidas** 🟢
Valida manejo de URLs incorrectas:
- ✓ No crashea con URLs inválidas
- ✓ Retorna código HTTP apropiado

#### **T008: Responsive Design** 🟡
Test parametrizado para 4 resoluciones:
- ✓ Desktop HD (1920x1080)
- ✓ Laptop (1366x768)
- ✓ Tablet (768x1024)
- ✓ Mobile (375x667)

Valida en cada resolución:
- ✓ Logo visible
- ✓ Navegación accesible
- ✓ CTA disponible
- ✓ Sin overflow horizontal

#### **T009: Seguridad** 🔴
Valida aspectos de seguridad:
- ✓ HTTPS obligatorio
- ✓ Sin mixed content (HTTP en HTTPS)
- ✓ Requests seguras

#### **T010: Performance** 🟡
Mide métricas de rendimiento:
- ✓ Tiempo de carga < 15s
- ✓ DOM Interactive < 5s
- ✓ Métricas de Navigation Timing

#### **T011: Navegación Principal** 🟡
Valida funcionalidad de navegación:
- ✓ Barra de navegación presente
- ✓ Enlaces funcionales
- ✓ Navegación al menú exitosa

#### **T012: Footer** 🟢
Verifica presencia de footer:
- ✓ Footer visible
- ✓ Contiene enlaces relevantes
- ✓ Información de contacto/legal

## 🚀 Instalación

### Prerequisitos
- Node.js 18+
- npm o yarn

### Setup
```bash
# Instalar dependencias
npm install

# Instalar browser de Playwright
npx playwright install chromium
```

## 🧪 Ejecutar Tests

### Comandos Principales

```bash
# Ejecutar toda la suite
npm test

# Modo UI (recomendado para desarrollo)
npm run test:ui

# Modo headed (ver el navegador)
npm run test:headed

# Debug mode
npm run test:debug

# Ver reporte
npm run report
```

### Tests Específicos

```bash
# Ejecutar un test específico
npx playwright test --grep "T001"

# Ejecutar solo tests críticos
npx playwright test --grep "T001|T002|T009"

# Ejecutar tests responsive
npx playwright test --grep "T008"
```

## 📊 Reportes

```bash
# Ver último reporte HTML
npm run report

# Ver trace de un test
npx playwright show-trace test-results/.../trace.zip
```

## 📁 Estructura del Proyecto

```
PizzaHut/
├── tests/
│   └── pizzahut.spec.js       # Suite limpia de 12 tests
├── screenshots/                # Screenshots automáticos
├── test-results/              # Resultados de ejecución
├── playwright-report/         # Reporte HTML
├── playwright.config.js       # Configuración
├── package.json
└── README.md
```

## 🛠️ Configuración

### playwright.config.js

```javascript
module.exports = {
  timeout: 60000,              // Timeout por test: 60s
  retries: 2,                  // Reintentos en CI
  workers: 4,                  // Tests en paralelo
  use: {
    baseURL: 'https://www.pizzahut.com.co',
    actionTimeout: 20000,      // 20s para acciones
    navigationTimeout: 45000,  // 45s para navegación
    screenshot: 'only-on-failure',
    video: 'retain-on-failure',
    trace: 'on-first-retry'
  }
}
```

## 🎯 Mejores Prácticas Implementadas

### ✅ Sin Anti-Patterns
- ❌ **ELIMINADO**: `waitForTimeout` arbitrarios
- ❌ **ELIMINADO**: Tests de diagnóstico en producción
- ❌ **ELIMINADO**: Lógica compleja con múltiples fallbacks
- ❌ **ELIMINADO**: Race conditions con Promise.race
- ❌ **ELIMINADO**: Tests inválidos (horarios del cliente)

### ✅ Código Limpio
- Selectores por role de ARIA
- Auto-waiting de Playwright
- Helpers reutilizables
- Código DRY

### ✅ Tests Robustos
- Aserciones claras
- Manejo apropiado de errores
- Tests independientes
- Sin flakiness

### ✅ Mantenibilidad
- Selectores centralizados
- Documentación inline
- Tests simples y directos

## 🔍 Debug de Tests

### Modo Debug Interactivo
```bash
npx playwright test --debug
```

### Inspector de Playwright
```bash
npx playwright test --ui
```

### Ver Trace
```bash
npx playwright show-trace test-results/..../trace.zip
```

## 📈 Métricas de Calidad

- **Total Tests**: 12 (16 incluyendo tests parametrizados)
- **Cobertura**: Funcionalidad principal, búsqueda, validación, responsive, seguridad, performance
- **Anti-patterns**: 0 ✅
- **waitForTimeout**: 0 ✅
- **Flakiness**: Minimizado con auto-waiting
- **Tiempo Ejecución**: ~5-8 minutos (suite completa)

## 🐛 Bugs Corregidos

### Version 3.0.0 - Reescritura Completa

#### ❌ Bugs Eliminados:

1. **waitForTimeout (5 ocurrencias)** 🔴 CRÍTICO
   - **Ubicación**: Líneas 62, 99, 201, 769, 803
   - **Problema**: Anti-pattern que causa flakiness
   - **Solución**: Reemplazados con auto-waiting de Playwright

2. **Test de Diagnóstico en Producción** 🔴 CRÍTICO
   - **Ubicación**: Líneas 793-847
   - **Problema**: Código de debug no debe estar en producción
   - **Solución**: Eliminado completamente

3. **Tests de Horarios Inválidos (T011, T012)** 🔴 CRÍTICO
   - **Ubicación**: Líneas 677-787
   - **Problema**: `page.clock` manipula tiempo del cliente, pero validaciones son del servidor
   - **Solución**: Reemplazados con tests reales (navegación y footer)

4. **Lógica Compleja con Múltiples Fallbacks** 🟡 MEDIO
   - **Ubicación**: T002 (líneas 185-274)
   - **Problema**: 3 estrategias de fallback indican selectores frágiles
   - **Solución**: Simplificado a un solo flujo con selectores robustos

5. **Race Conditions con Promise.race** 🟡 MEDIO
   - **Ubicación**: Línea 254
   - **Problema**: Promise.race puede fallar inesperadamente
   - **Solución**: Eliminado, usando solo auto-waiting

6. **Selectores Frágiles** 🟡 MEDIO
   - **Ubicación**: Múltiples lugares
   - **Problema**: `[class*="..."]` son frágiles
   - **Solución**: Priorizados roles ARIA y data-testid

7. **Manejo de Errores Inconsistente** 🟢 BAJO
   - **Ubicación**: Múltiples catch blocks
   - **Problema**: Catch blocks vacíos o con console.log
   - **Solución**: Manejo específico con test.skip() cuando corresponde

8. **Screenshot de Debug en Flujo Principal** 🟢 BAJO
   - **Ubicación**: T002 líneas 231, 246
   - **Problema**: Screenshots de debug no deben estar en tests principales
   - **Solución**: Eliminados

#### ✅ Mejoras Adicionales:

- **Selectores más robustos**: Priorizan data-testid y roles ARIA
- **Tests más simples**: Cada test tiene un solo propósito claro
- **Mejor documentación**: Código auto-explicativo
- **Sin código muerto**: Eliminadas estrategias fallback complejas
- **Timeouts consistentes**: Todos los waits tienen timeout explícito

## 🤝 Contribuir

1. Fork el proyecto
2. Crea una rama (`git checkout -b feature/nueva-funcionalidad`)
3. Sigue las mejores prácticas:
   - ❌ NO uses `waitForTimeout`
   - ✅ USA auto-waiting de Playwright
   - ✅ USA selectores por role cuando sea posible
   - ✅ DOCUMENTA el propósito del test
4. Asegúrate que todos los tests pasen
5. Commit (`git commit -m 'Add: nueva funcionalidad'`)
6. Push y abre un Pull Request

## 📚 Recursos

- [Playwright Documentation](https://playwright.dev)
- [Best Practices Guide](https://playwright.dev/docs/best-practices)
- [Pizza Hut Colombia](https://www.pizzahut.com.co)

## 📝 Changelog

### Version 3.0.0 - Reescritura Completa (2024-11-13)
- 🔥 Eliminados TODOS los anti-patterns
- ✅ Tests 100% ejecutables y confiables
- 🎯 12 tests limpios y bien planteados
- 📝 Documentación actualizada
- ⚡ Mejora significativa en confiabilidad

### Version 2.1.0 - Correcciones Previas
- Correcciones parciales de bugs

### Version 2.0.0 - Premium Suite
- Suite inicial con 10 tests

## 📄 Licencia

ISC

---

**Autor**: Sara Buriticá  
**Versión**: 3.0.0 - Reescritura Completa  
**Última actualización**: Noviembre 13, 2024  
**Estado**: ✅ Producción Ready - Cero anti-patterns, tests ejecutables
