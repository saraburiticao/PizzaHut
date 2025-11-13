# 📋 TEST CASES - PIZZA HUT COLOMBIA

## 📊 Resumen Ejecutivo

**Proyecto:** Pizza Hut Colombia - Suite de Pruebas Automatizadas  
**Framework:** Playwright  
**Total de Test Cases:** 10 casos de prueba principales  
**Fecha de Documentación:** Noviembre 2024  
**Estado:** Implementados y Operativos

---

## 🎯 Objetivos de las Pruebas

Esta suite de pruebas tiene como objetivo verificar la funcionalidad, usabilidad, rendimiento y seguridad del sitio web de Pizza Hut Colombia, garantizando una experiencia de usuario óptima en todos los aspectos del sitio.

### Áreas de Cobertura
- ✅ Funcionalidad principal del sitio
- ✅ Flujo de navegación y visualización de productos
- ✅ Validaciones y manejo de errores
- ✅ Diseño responsive
- ✅ Seguridad y rendimiento
- ✅ Navegación y estructura

---

## 📚 Clasificación de Test Cases

### Distribución por Tipo
- **✅ Happy Path:** 8 casos (80%)
- **❌ Fail Path:** 2 casos (20%)
- **⚡ Edge Cases:** 0 casos (0%)

### Nota Importante
❌ **Tests de Búsqueda (T004, T005):** Eliminados - El sitio no cuenta con campo de búsqueda disponible.

---

# 🎯 HAPPY PATH - Casos de Éxito

Los casos de **Happy Path** validan que las funcionalidades principales del sitio web funcionen correctamente bajo condiciones normales y esperadas.

---

## T001: Carga de Página Principal con Elementos Críticos

**Tipo:** ✅ Happy Path  
**Categoría:** Funcionalidad Principal  
**Prioridad:** Alta

### Descripción
Verifica que la página principal del sitio cargue correctamente con todos sus elementos esenciales visibles y funcionales.

### Precondiciones
- Navegador compatible (Chrome, Firefox, Safari)
- Conexión a internet estable
- URL base: `https://www.pizzahut.com.co/`

### Pasos de Ejecución
1. Navegar a la URL principal de Pizza Hut Colombia
2. Aceptar cookies si aparece el banner
3. Esperar carga completa de la página (evento `load`)
4. Verificar presencia de elementos críticos

### Validaciones
- ✓ **V1:** Título de página contiene "Pizza Hut" (case insensitive)
- ✓ **V2:** URL utiliza protocolo HTTPS
- ✓ **V3:** URL contiene dominio "pizzahut.com.co"
- ✓ **V4:** Elemento de navegación (`<nav>`) está visible
- ✓ **V5:** Logo de Pizza Hut está visible
- ✓ **V6:** CTA principal (Menú/Ordenar/Pedir) está visible
- ✓ **V7:** No hay errores críticos en consola (excluyendo favicon, analytics, GTM, Google, reCAPTCHA)

### Resultado Esperado
Todos los elementos críticos cargados correctamente sin errores de consola relevantes.

### Evidencia
- Screenshot: `T001-homepage-loaded.png` (fullPage)
- Console logs: Reporte de errores filtrados

### Notas
- Errores de consola son reportados pero no fallan el test
- Se excluyen errores comunes de terceros (analytics, GTM)

---

## T002: Navegación al Menú y Visualización de Productos

**Tipo:** ✅ Happy Path  
**Categoría:** Flujo de Compra  
**Prioridad:** Alta

### Descripción
Valida que un usuario pueda navegar exitosamente a la sección del menú y visualizar productos disponibles con su información básica.

### Precondiciones
- Página principal cargada correctamente
- Link de navegación al menú disponible

### Pasos de Ejecución
1. Navegar a la página principal
2. Aceptar cookies si aparece banner
3. Hacer clic en el enlace "Menú" o similar
4. Esperar carga completa de la página del menú
5. Verificar visualización de productos

### Validaciones
- ✓ **V1:** URL cambia y contiene "menu", "carta", "productos" o "pizzas"
- ✓ **V2:** Página carga completamente (evento `load`)
- ✓ **V3:** Al menos 1 producto es visible (timeout: 15 segundos)
- ✓ **V4:** Primer producto tiene título/nombre visible
- ✓ **V5:** Primer producto tiene precio visible
- ✓ **V6:** Primer producto tiene botón de acción visible

### Resultado Esperado
Usuario navega al menú exitosamente y visualiza productos con información completa.

### Evidencia
- Screenshot: `T002-menu-products.png` (fullPage)
- Console log: Cantidad de productos encontrados
- Console log: Nombre del primer producto

---

## T003: Productos con Botones Interactivos

**Tipo:** ✅ Happy Path  
**Categoría:** Flujo de Compra  
**Prioridad:** Alta

### Descripción
Verifica que los productos mostrados en el menú tengan botones interactivos funcionales (visibles, habilitados, con texto).

### Precondiciones
- Página del menú cargada
- Productos visibles en la página

### Pasos de Ejecución
1. Navegar al menú
2. Localizar el primer producto
3. Verificar presencia de botón de acción
4. Validar estado del botón

### Validaciones
- ✓ **V1:** Botón de acción está visible (timeout: 5 segundos)
- ✓ **V2:** Botón está habilitado (no disabled)
- ✓ **V3:** Botón contiene texto no vacío
- ✓ **V4:** Botón es clickeable

### Resultado Esperado
Botones de productos son completamente funcionales e interactivos.

### Evidencia
- Screenshot: `T003-product-buttons.png`
- Console log: Texto del botón encontrado

---

## T008-Desktop-HD: Responsividad en Resolución 1920x1080

**Tipo:** ✅ Happy Path  
**Categoría:** Responsive Design  
**Prioridad:** Alta

### Descripción
Verifica que el sitio sea completamente funcional en resolución Desktop HD estándar.

### Configuración
- Viewport: 1920x1080 píxeles
- Dispositivo simulado: Desktop HD

### Pasos de Ejecución
1. Configurar viewport a 1920x1080
2. Navegar a la página principal
3. Aceptar cookies
4. Verificar elementos y layout

### Validaciones
- ✓ **V1:** Logo visible y bien posicionado
- ✓ **V2:** Navegación accesible y completa
- ✓ **V3:** CTA principal visible y clickeable
- ✓ **V4:** No hay scroll horizontal no deseado (tolerancia: 5px)
- ✓ **V5:** Body width ≤ viewport width + 5px

### Resultado Esperado
Sitio 100% funcional y visualmente correcto en Desktop HD.

### Evidencia
- Screenshot: `T008-responsive-desktop-hd.png`

---

## T008-Laptop: Responsividad en Resolución 1366x768

**Tipo:** ✅ Happy Path  
**Categoría:** Responsive Design  
**Prioridad:** Alta

### Descripción
Verifica funcionalidad en resolución de laptop estándar.

### Configuración
- Viewport: 1366x768 píxeles
- Dispositivo simulado: Laptop típico

### Validaciones
- ✓ Logo visible
- ✓ Navegación accesible
- ✓ CTA principal visible
- ✓ Sin scroll horizontal (tolerancia: 5px)
- ✓ Elementos no se superponen

### Resultado Esperado
Sitio completamente funcional en laptops estándar.

### Evidencia
- Screenshot: `T008-responsive-laptop.png`

---

## T008-Tablet: Responsividad en Resolución 768x1024

**Tipo:** ✅ Happy Path  
**Categoría:** Responsive Design  
**Prioridad:** Media

### Descripción
Valida la experiencia en dispositivos tablet (orientación portrait).

### Configuración
- Viewport: 768x1024 píxeles
- Dispositivo simulado: iPad/Tablet

### Validaciones
- ✓ Logo visible
- ✓ Navegación adaptada (puede incluir menú colapsado)
- ✓ CTA principal accesible
- ✓ Sin scroll horizontal
- ✓ Touch targets apropiados

### Resultado Esperado
Experiencia optimizada para tablets con navegación adaptativa.

### Evidencia
- Screenshot: `T008-responsive-tablet.png`

---

## T008-Mobile: Responsividad en Resolución 375x667

**Tipo:** ✅ Happy Path  
**Categoría:** Responsive Design  
**Prioridad:** Alta

### Descripción
Verifica experiencia móvil en dispositivos pequeños (iPhone SE/8).

### Configuración
- Viewport: 375x667 píxeles
- Dispositivo simulado: iPhone SE

### Validaciones
- ✓ Logo visible en versión móvil
- ✓ Menú hamburguesa o navegación móvil funcional
- ✓ CTA principal visible y accesible
- ✓ Sin scroll horizontal
- ✓ Elementos táctiles ≥ 44x44px
- ✓ Texto legible sin zoom

### Resultado Esperado
Experiencia móvil optimizada y completamente funcional.

### Evidencia
- Screenshot: `T008-responsive-mobile.png`

---

## T009: Uso de HTTPS y Seguridad Básica

**Tipo:** ✅ Happy Path  
**Categoría:** Seguridad  
**Prioridad:** Crítica

### Descripción
Valida que el sitio implemente protocolo HTTPS y no tenga contenido mixto (mixed content).

### Precondiciones
- Acceso al sitio web
- Monitoreo de requests activo

### Pasos de Ejecución
1. Configurar listener de requests
2. Navegar a la página principal
3. Esperar carga completa
4. Analizar protocolo y requests

### Validaciones
- ✓ **V1:** URL utiliza HTTPS (protocolo seguro)
- ✓ **V2:** No hay requests HTTP inseguras en página HTTPS
- ✓ **V3:** Mixed content ausente o mínimo

### Resultado Esperado
Sitio usa HTTPS exclusivamente sin contenido mixto.

### Evidencia
- Screenshot: `T009-security-check.png`
- Console log: Reporte de requests inseguras (si existen)

### Notas
- Requests HTTP generan warning pero no fallan el test
- Se reportan las primeras 3 requests inseguras para análisis

---

## T010: Rendimiento de Carga Aceptable

**Tipo:** ✅ Happy Path  
**Categoría:** Performance  
**Prioridad:** Alta

### Descripción
Mide y valida que el sitio cargue en tiempos aceptables con métricas de rendimiento razonables.

### Métricas Monitoreadas
- Tiempo total de carga (página completa)
- DOM Interactive
- DOM Content Loaded

### Pasos de Ejecución
1. Iniciar cronómetro
2. Navegar a página principal
3. Esperar evento `load`
4. Capturar métricas de rendimiento
5. Calcular tiempos

### Validaciones
- ✓ **V1:** Tiempo total de carga < 15 segundos
- ✓ **V2:** DOM Interactive < 5 segundos
- ✓ **V3:** DOM Content Loaded medido y reportado
- ✓ **V4:** Métricas de performance disponibles

### Resultado Esperado
Sitio carga en tiempo razonable con métricas dentro de umbrales aceptables.

### Evidencia
- Screenshot: `T010-performance-check.png`
- Console log: Tiempo total de carga en ms
- Console log: DOM Interactive en ms
- Console log: DOM Content Loaded en ms

### Umbrales de Performance
- **Excelente:** < 3 segundos
- **Bueno:** 3-8 segundos
- **Aceptable:** 8-15 segundos
- **Lento:** > 15 segundos

---

## T011: Navegación Principal Funcional

**Tipo:** ✅ Happy Path  
**Categoría:** Navegación  
**Prioridad:** Alta

### Descripción
Valida que la navegación principal del sitio esté presente, visible y funcional con enlaces operativos.

### Precondiciones
- Página principal cargada
- Elementos de navegación presentes

### Pasos de Ejecución
1. Navegar a la página principal
2. Aceptar cookies
3. Verificar presencia de navegación
4. Contar enlaces de navegación
5. Hacer clic en enlace del menú
6. Verificar navegación exitosa

### Validaciones
- ✓ **V1:** Elemento `<nav>` está visible
- ✓ **V2:** Hay más de 2 enlaces de navegación
- ✓ **V3:** Enlace "Menú" está visible
- ✓ **V4:** Click en "Menú" navega a nueva URL
- ✓ **V5:** Nueva URL es diferente de la homepage

### Resultado Esperado
Navegación principal funcional con enlaces operativos que redirigen correctamente.

### Evidencia
- Screenshot: `T011-navigation.png` (fullPage)
- Console log: Cantidad de enlaces encontrados
- Console log: URL destino después de click

---

## T012: Footer con Información Relevante

**Tipo:** ✅ Happy Path  
**Categoría:** Estructura  
**Prioridad:** Baja

### Descripción
Verifica que el footer del sitio esté presente, visible y contenga información relevante con enlaces funcionales.

### Precondiciones
- Página principal cargada completamente

### Pasos de Ejecución
1. Navegar a la página principal
2. Aceptar cookies
3. Esperar carga completa
4. Localizar elemento `<footer>`
5. Contar enlaces dentro del footer

### Validaciones
- ✓ **V1:** Elemento `<footer>` está visible
- ✓ **V2:** Footer contiene al menos 1 enlace
- ✓ **V3:** Enlaces son accesibles

### Resultado Esperado
Footer presente con información y enlaces relevantes.

### Evidencia
- Screenshot: `T012-footer.png`
- Console log: Cantidad de enlaces en footer

---

# ❌ FAIL PATH - Casos de Error y Fallo

Los casos de **Fail Path** validan que el sistema maneje correctamente situaciones de error, entradas inválidas y condiciones adversas.

---

## T006: Validación de Email Inválido en Formularios

**Tipo:** ❌ Fail Path  
**Categoría:** Validaciones  
**Prioridad:** Media

### Descripción
Verifica que los formularios del sitio validen correctamente emails inválidos y rechacen formatos incorrectos.

### Precondiciones
- Formulario con campo email disponible (newsletter, contacto, etc.)

### Pasos de Ejecución
1. Navegar a la página principal
2. Localizar formulario con campo email
3. **Caso 1:** Ingresar email sin @ ("email-sin-arroba")
4. Validar rechazo mediante HTML5 validation
5. **Caso 2:** Ingresar email válido ("test@ejemplo.com")
6. Validar aceptación

### Validaciones
- ✓ **V1:** Email sin @ es marcado como inválido (`checkValidity()` = false)
- ✓ **V2:** Validación HTML5 funciona correctamente
- ✓ **V3:** Email válido es aceptado (`checkValidity()` = true)
- ✓ **V4:** No hay errores en el proceso de validación

### Resultado Esperado
- Emails inválidos son rechazados con validación HTML5
- Emails válidos son aceptados sin restricciones
- Formulario mantiene integridad de validación

### Evidencia
- Screenshot: `T006-form-validation.png`
- Console log: Confirmación de validación inválida
- Console log: Confirmación de validación válida

### Notas
- Test se omite si no hay formularios con campo email
- Se valida usando `HTMLInputElement.checkValidity()`

---

## T007: Manejo de Rutas Inexistentes (404)

**Tipo:** ❌ Fail Path  
**Categoría:** Manejo de Errores  
**Prioridad:** Media

### Descripción
Valida que el sitio maneje correctamente rutas inexistentes sin crashear, retornando código HTTP apropiado.

### Precondiciones
- Acceso al sitio web
- Ruta inexistente: `/pagina-que-no-existe-abc123xyz`

### Pasos de Ejecución
1. Navegar a URL inexistente
2. Observar respuesta del servidor
3. Verificar código de estado HTTP
4. Capturar evidencia

### Validaciones
- ✓ **V1:** Request completa sin timeout
- ✓ **V2:** Código de respuesta HTTP está definido
- ✓ **V3:** Código es 200, 302 o 404 (comportamientos válidos)
- ✓ **V4:** Sistema no crashea
- ✓ **V5:** Página carga (aunque sea error page)

### Resultado Esperado
Sistema maneja ruta inexistente correctamente sin crashes, con código HTTP apropiado.

### Evidencia
- Screenshot: `T007-404-page.png` (fullPage)
- Console log: Código de respuesta HTTP

### Notas
- Algunos sitios redirigen 404 a homepage (302) - válido
- Otros muestran página de error custom (200) - válido
- Error 404 estándar también es válido
- Lo crítico es que no crashee

---

# ⚡ EDGE CASES - Casos Límite

Los casos de **Edge Cases** validan el comportamiento del sistema en situaciones límite, condiciones inusuales o escenarios extremos.

---

**📝 Nota:** Actualmente no hay Edge Cases implementados en esta suite. Se recomienda agregar casos para:

### Sugerencias de Edge Cases Futuros:
- Formularios con emails extremadamente largos (> 254 caracteres)
- Formularios con caracteres especiales en campos de texto (ñ, tildes, emojis)
- Navegación con JavaScript deshabilitado
- Carga con conexión lenta (throttling 3G)
- Múltiples clicks rápidos en botones (prevención de doble submit)
- Carrito con cantidades extremas (999+ productos)
- Viewport extremadamente pequeño (< 320px) o grande (> 2560px)
- Timeout de sesión durante flujo de compra
- Horarios límite (justo cuando abre/cierra el servicio)
- Navegación con combinaciones de teclas (keyboard only navigation)
- Productos sin imagen o con imágenes rotas

---

# 🛠️ HERRAMIENTAS Y CONFIGURACIÓN

## Clase Helper: PizzaHutPage

Helper class que centraliza selectores y métodos reutilizables para todos los tests.

### Propósito
- Centralizar selectores robustos
- Reutilizar lógica común
- Facilitar mantenimiento
- Mejorar legibilidad de tests

### Selectores Principales

```javascript
get menuLink()      // Enlaces al menú
get searchInput()   // Campo de búsqueda
get cartButton()    // Botón del carrito
```

### Métodos Reutilizables

```javascript
async navigateToMenu()      // Navega al menú con esperas apropiadas
async acceptCookies()       // Acepta banner de cookies automáticamente
async waitForPageStable()   // Espera carga completa (DOM + network)
```

### Características
- Selectores con fallbacks múltiples
- Manejo automático de timeouts
- Logging informativo
- Esperas inteligentes (sin waits arbitrarios)

---

## 📊 Estrategia de Ejecución

### Orden Recomendado de Ejecución

#### 1. Smoke Tests (Críticos)
```
T001: Carga de homepage
T009: HTTPS
```

#### 2. Funcionalidad Core
```
T002: Navegación al menú
T003: Botones interactivos
T011: Navegación principal
```

#### 3. Validaciones
```
T006: Validación de email (Fail Path)
T007: Ruta 404 (Fail Path)
```

#### 4. Cross-Device (Responsive)
```
T008-Desktop-HD
T008-Laptop
T008-Tablet
T008-Mobile
```

#### 5. Performance y Estructura
```
T010: Performance
T012: Footer
```

### Frecuencia de Ejecución

| Ambiente | Tests | Frecuencia |
|----------|-------|------------|
| **CI/CD** | T001, T002, T009, T011 | Cada commit |
| **Nightly** | Suite completa | Diario |
| **Pre-release** | Suite completa + regresión | Antes de cada release |
| **Producción** | T001, T009, T010 | Cada hora |

### Configuración Playwright

```javascript
// playwright.config.js
{
  timeout: 30000,           // Timeout global
  retries: 2,               // Reintentos en fallo
  use: {
    screenshot: 'only-on-failure',
    video: 'retain-on-failure',
    trace: 'on-first-retry'
  }
}
```

---

## ✅ Criterios de Éxito y Fallo

### ✅ Test PASA si:
- ✓ Todas las validaciones especificadas se cumplen
- ✓ No hay errores críticos (JavaScript, timeouts)
- ✓ Screenshots se generan correctamente
- ✓ Tiempos de respuesta dentro de umbrales
- ✓ Elementos esperados son encontrados
- ✓ Navegación funciona correctamente

### ❌ Test FALLA si:
- ✗ Cualquier validación crítica falla
- ✗ Timeout excede límite (30 segundos default)
- ✗ Elementos esperados no se encuentran
- ✗ Errores JavaScript críticos detectados
- ✗ Navegación no funciona
- ✗ Performance fuera de umbrales
- ✗ Seguridad comprometida (no HTTPS)

### ⚠️ Test se OMITE si:
- ⊘ Funcionalidad no está disponible (búsqueda, formularios)
- ⊘ Elementos no existen en la página actual
- ⊘ Feature flags deshabilitados
- ⊘ Ambiente no soporta la funcionalidad

---

## 📈 Métricas y Reportes

### Información Capturada por Cada Test

| Tipo de Dato | Descripción | Uso |
|--------------|-------------|-----|
| **Screenshots** | Evidencia visual completa | Debugging, reportes |
| **Console Logs** | Mensajes informativos | Análisis, debugging |
| **Errores JS** | Errores de consola capturados | Detección de bugs |
| **Métricas Performance** | Tiempos de carga | Optimización |
| **Network Timing** | Requests lentas | Identificar cuellos de botella |
| **Element Counts** | Cantidad de elementos | Validación de contenido |

### Ubicación de Evidencias

```
/screenshots/
  ├── T001-homepage-loaded.png
  ├── T002-menu-products.png
  ├── T003-product-buttons.png
  ├── T006-form-validation.png
  ├── T007-404-page.png
  ├── T008-responsive-desktop-hd.png
  ├── T008-responsive-laptop.png
  ├── T008-responsive-tablet.png
  ├── T008-responsive-mobile.png
  ├── T009-security-check.png
  ├── T010-performance-check.png
  ├── T011-navigation.png
  └── T012-footer.png
```

### Reportes Generados

1. **HTML Report** (Playwright nativo)
   - Vista interactiva de resultados
   - Screenshots embebidos
   - Trazas de ejecución
   - Logs de consola

2. **JUnit XML** (para CI/CD)
   - Integración con Jenkins, GitLab CI
   - Métricas de éxito/fallo
   - Tiempos de ejecución

3. **Custom Logs** (console)
   - Mensajes informativos en tiempo real
   - Contadores y estadísticas
   - Warnings y alertas

---

## 🔧 Mantenimiento y Mejora Continua

### Buenas Prácticas Implementadas

✅ **Tests Determinísticos**
- Sin `waitForTimeout()` arbitrarios
- Esperas basadas en eventos del DOM
- Selectores robustos con fallbacks

✅ **Código Limpio**
- Helper class centralizada
- Métodos reutilizables
- Nombres descriptivos
- Comentarios relevantes

✅ **Aserciones Completas**
- Validaciones explícitas numeradas
- Timeouts configurados apropiadamente
- Mensajes de error claros

✅ **Evidencia Exhaustiva**
- Screenshots automáticos
- Logs informativos
- Métricas capturadas
- Trazas de ejecución

✅ **Manejo de Errores**
- Try-catch donde es apropiado
- Tests condicionales (skip si no aplica)
- Fallbacks para elementos opcionales
- Reportes de errores no críticos

### Cuándo Actualizar los Tests

| Evento | Acción Requerida | Prioridad |
|--------|------------------|-----------|
| **Cambio de UI** | Actualizar selectores | Alta |
| **Nueva funcionalidad** | Agregar nuevos tests | Media |
| **Modificación de flujos** | Actualizar steps y validaciones | Alta |
| **Cambio de URLs** | Actualizar rutas esperadas | Crítica |
| **Actualización Playwright** | Revisar compatibilidad | Media |
| **Fallo recurrente** | Investigar y fortalecer test | Alta |

### Proceso de Actualización

1. **Identificar cambio** en el sitio o test
2. **Actualizar selectores** si es necesario
3. **Ejecutar test localmente** para verificar
4. **Actualizar documentación** (este documento)
5. **Commit con descripción clara** del cambio
6. **Ejecutar suite completa** en CI/CD
7. **Verificar reportes** de ejecución

---

## 📞 Información Técnica

### Tecnologías Utilizadas

| Componente | Versión | Propósito |
|------------|---------|-----------|
| **Playwright** | 1.x | Framework de testing |
| **Node.js** | 18+ | Runtime de JavaScript |
| **JavaScript** | ES6+ | Lenguaje de programación |

### Requisitos del Sistema

- **Sistema Operativo:** Windows, macOS, Linux
- **Node.js:** v18.0.0 o superior
- **NPM:** v9.0.0 o superior
- **RAM:** Mínimo 4GB, recomendado 8GB
- **Espacio en Disco:** 500MB para dependencias

### Comandos Útiles

```bash
# Instalar dependencias
npm install

# Ejecutar todos los tests
npx playwright test

# Ejecutar un test específico
npx playwright test tests/pizzahut.spec.js -g "T001"

# Ejecutar con UI mode
npx playwright test --ui

# Ejecutar solo Happy Path
npx playwright test tests/pizzahut.spec.js -g "T001|T002|T003|T008|T009|T010|T011|T012"

# Ejecutar solo Fail Path
npx playwright test tests/pizzahut.spec.js -g "T006|T007"

# Ver reporte HTML
npx playwright show-report

# Ejecutar en un navegador específico
npx playwright test --project=chromium
npx playwright test --project=firefox
npx playwright test --project=webkit

# Ejecutar con debug
npx playwright test --debug

# Generar screenshots actualizados
npx playwright test --update-snapshots
```

---

## 📝 Notas Finales y Limitaciones

### Tests Condicionales

Algunos tests se omiten automáticamente (`test.skip()`) si:
- ⊘ Funcionalidad no está disponible (búsqueda, formularios)
- ⊘ Elementos no existen en la página actual
- ⊘ Feature flags deshabilitados
- ⊘ Campo de búsqueda no visible

### Limitaciones Conocidas

1. **Selectores Dinámicos**
   - Algunos elementos tienen IDs/clases dinámicas
   - Se usan múltiples estrategias de selección (roles, texto, atributos)

2. **Contenido Dinámico**
   - Productos pueden cambiar según inventario
   - Tests se adaptan a disponibilidad actual

3. **Performance Variables**
   - Métricas pueden variar según:
     - Red del ejecutor
     - Carga del servidor
     - CDN y caching
     - Hora del día

4. **Cookies y Banners**
   - Banner de cookies puede no aparecer siempre
   - Se maneja con try-catch (no crítico)

5. **Third-party Scripts**
   - Analytics, GTM, reCAPTCHA pueden causar errores
   - Se filtran de validaciones críticas

### Recomendaciones Futuras

#### Tests Adicionales Sugeridos
- ✨ Agregar producto al carrito (T013)
- ✨ Modificar cantidad en carrito (T014)
- ✨ Proceso de checkout completo (T015)
- ✨ Selección de ubicación/tienda (T016)
- ✨ Aplicación de cupones/descuentos (T017)
- ✨ Edge Cases con caracteres especiales (T018)
- ✨ Verificación de accesibilidad (WCAG) (T019)
- ✨ Tests de integración con APIs (T020)

#### Mejoras Técnicas
- 🔧 Implementar Page Object Model (POM) completo
- 🔧 Agregar tests de accesibilidad con `@axe-core/playwright`
- 🔧 Integrar con herramientas de monitoreo (DataDog, New Relic)
- 🔧 Agregar tests visuales con Percy o Applitools
- 🔧 Implementar paralelización por categoría
- 🔧 Crear dashboard custom de métricas

#### Documentación
- 📚 Video tutorials de ejecución
- 📚 Guía de troubleshooting
- 📚 FAQ de errores comunes
- 📚 Arquitectura de tests detallada

---

## 📊 Estadísticas de la Suite

### Resumen General

| Métrica | Valor |
|---------|-------|
| **Total Tests** | 10 |
| **Happy Path** | 8 (80%) |
| **Fail Path** | 2 (20%) |
| **Edge Cases** | 0 (0%) |
| **Tiempo Estimado** | ~4-6 minutos (secuencial) |
| **Tiempo Paralelo** | ~2-3 minutos (4 workers) |
| **Cobertura de Funcionalidad** | ~65% |

### Distribución por Prioridad

| Prioridad | Cantidad | Porcentaje |
|-----------|----------|------------|
| **Crítica** | 1 | 10% |
| **Alta** | 7 | 70% |
| **Media** | 1 | 10% |
| **Baja** | 1 | 10% |

**Nota:** Los 4 tests de Responsive (T008) se cuentan individualmente en las estadísticas.

### Distribución por Categoría

| Categoría | Tests | Tipo Predominante |
|-----------|-------|-------------------|
| **Funcionalidad Principal** | 1 | Happy Path |
| **Flujo de Compra** | 2 | Happy Path |
| **Validaciones** | 2 | Fail Path |
| **Responsive** | 4 | Happy Path |
| **Seguridad** | 1 | Happy Path |
| **Performance** | 1 | Happy Path |
| **Navegación** | 2 | Happy Path |
| **Estructura** | 1 | Happy Path |

**Total:** 14 tests (contando cada variante de T008 por separado)

---

## 🎓 Glosario de Términos

| Término | Definición |
|---------|------------|
| **Happy Path** | Flujo normal y esperado donde todo funciona correctamente |
| **Fail Path** | Escenarios de error donde el sistema debe manejar fallos apropiadamente |
| **Edge Case** | Situaciones límite o inusuales que pueden causar comportamientos inesperados |
| **Smoke Test** | Tests básicos que verifican funcionalidad crítica |
| **Regression Test** | Tests que verifican que funcionalidades existentes no se rompan |
| **Flaky Test** | Test que falla intermitentemente sin cambios en el código |
| **Deterministic Test** | Test que produce siempre el mismo resultado con las mismas condiciones |
| **Mixed Content** | Contenido HTTP en página HTTPS (riesgo de seguridad) |
| **DOM** | Document Object Model - estructura del HTML |
| **Viewport** | Área visible del navegador |
| **Selector** | Forma de identificar elementos en la página (CSS, XPath, role, etc.) |

---

**📅 Última Actualización:** Noviembre 2024  
**👤 Documentado por:** Equipo de QA Automation  
**🔄 Versión:** 1.0  

---

**¡Suite de pruebas organizada por tipo de caso: Happy Path, Fail Path y Edge Cases! 🍕✅❌⚡**
