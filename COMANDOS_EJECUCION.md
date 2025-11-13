# 🎮 Comandos de Ejecución - Pizza Hut Tests

## 📋 Comandos Básicos

### Instalación Inicial

```powershell
cd "C:\Users\SARA\Documents\DOCS personales\personal\Laboral MI PC\JHON\plawright\proyectos\PizzaHut"
npm install
npx playwright install
```

### Ejecución Principal

```powershell
# Ejecutar todos los tests (headless)
npm test

# Ver tests ejecutándose (con navegador visible)
npm run test:headed

# Modo UI interactivo (RECOMENDADO PARA DESARROLLO)
npm run test:ui

# Debug paso a paso
npm run test:debug
```

## 🌐 Por Navegador

```powershell
# Solo Chromium/Chrome
npm run test:chromium

# Solo Firefox
npm run test:firefox

# Solo Safari/WebKit
npm run test:webkit

# Mobile Chrome
npm run test:mobile
```

## 🎯 Por Categoría de Tests

```powershell
# Solo Happy Path (flujos exitosos)
npm run test:happy

# Solo Fail Path (casos de error)
npm run test:fail

# Solo Edge Cases (casos límite)
npm run test:edge
```

## 📊 Tests Específicos

```powershell
# Ejecutar un solo test por ID
npx playwright test -g "HP-001"

# Ejecutar tests de carrito
npx playwright test -g "carrito"

# Ejecutar tests de búsqueda
npx playwright test -g "buscar|search"

# Ejecutar todos los Happy Path
npx playwright test -g "Happy Path"
```

## 🔍 Debugging y Análisis

```powershell
# Ver reporte HTML
npm run report

# Abrir trace viewer
npx playwright show-trace test-results/[ruta-del-trace]/trace.zip

# Ver solo tests que fallaron
npx playwright test --reporter=list --only-failures

# Ejecutar con más información
npx playwright test --reporter=list
```

## 🎨 Generación de Código

```powershell
# Generar tests automáticamente (codegen)
npm run codegen

# Codegen en modo móvil
npx playwright codegen --device="iPhone 12" https://www.pizzahut.com.co

# Codegen con storage state (cookies/localStorage guardados)
npx playwright codegen --save-storage=auth.json https://www.pizzahut.com.co
```

## ⚙️ Configuración Avanzada

```powershell
# Ejecutar en paralelo (4 workers)
npx playwright test --workers=4

# Ejecutar secuencialmente
npx playwright test --workers=1

# Ejecutar con timeout mayor
npx playwright test --timeout=60000

# Solo tests marcados como @smoke
npx playwright test --grep @smoke

# Excluir tests específicos
npx playwright test --grep-invert @slow
```

## 📸 Screenshots y Videos

```powershell
# Ver screenshots generados
cd screenshots
dir

# Ver videos de tests fallidos
cd test-results
dir
```

## 🔄 Re-ejecutar Tests Fallidos

```powershell
# Solo ejecutar los que fallaron la última vez
npx playwright test --last-failed

# Re-intentar tests fallidos 3 veces
npx playwright test --retries=3
```

## 📦 Múltiples Proyectos

```powershell
# Ver lista de proyectos configurados
npx playwright test --list

# Ejecutar solo proyectos específicos
npx playwright test --project=chromium --project=firefox
```

## 🌍 Variables de Entorno

```powershell
# Con variable de entorno personalizada
$env:BASE_URL="https://www.pizzahut.com.co"; npm test

# Modo CI (Continuous Integration)
$env:CI="true"; npm test
```

## 🛠️ Mantenimiento

```powershell
# Actualizar Playwright
npm install @playwright/test@latest

# Re-instalar navegadores después de actualizar
npx playwright install

# Limpiar cache
npx playwright cache clear

# Verificar instalación
npx playwright --version
```

## 📝 Reportes Personalizados

```powershell
# Generar reporte JSON
npx playwright test --reporter=json > results.json

# Generar reporte JUnit (para CI/CD)
npx playwright test --reporter=junit

# Múltiples reportes a la vez
npx playwright test --reporter=html --reporter=json
```

## 🎯 Comando Completo (TODO EN UNO)

```powershell
# Instalar, configurar y ejecutar todo
cd "C:\Users\SARA\Documents\DOCS personales\personal\Laboral MI PC\JHON\plawright\proyectos\PizzaHut" ; npm install ; npx playwright install ; npm run test:ui
```

## ⚡ Atajos Rápidos

```powershell
# Alias útil: Copiar en tu PowerShell profile
function pw-test { npm test }
function pw-ui { npm run test:ui }
function pw-debug { npm run test:debug }
function pw-report { npm run report }
function pw-codegen { npm run codegen }

# Uso:
pw-ui
pw-report
```

## 🆘 Comandos de Ayuda

```powershell
# Ver ayuda de Playwright
npx playwright test --help

# Ver ayuda de codegen
npx playwright codegen --help

# Listar todos los tests sin ejecutarlos
npx playwright test --list
```

---

## 💡 TIPS

1. Usa `npm run test:ui` para desarrollo - es el más visual y útil
2. Usa `npm run test:headed` para ver qué hace cada test
3. Usa `npm run codegen` cuando necesites crear nuevos tests rápido
4. Siempre revisa el reporte después de ejecutar: `npm run report`

---

**Guarda este archivo como referencia rápida!** 📌

