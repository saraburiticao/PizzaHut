# 🚀 Guía Rápida - Pizza Hut Tests

## ⚡ Inicio Rápido

### 1. Instalar y Ejecutar

```bash
# En el directorio PizzaHut
cd PizzaHut

# Instalar dependencias
npm install

# Instalar navegadores
npx playwright install

# Ejecutar tests
npm test
```

## 📊 Comandos Más Usados

### Ejecución Básica

```bash
# Ver tests mientras se ejecutan
npm run test:headed

# Modo UI interactivo (RECOMENDADO)
npm run test:ui

# Debug paso a paso
npm run test:debug
```

### Ejecutar Tests Específicos

```bash
# Solo un archivo
npx playwright test tests/pizzahut.spec.js

# Solo un test específico por nombre
npx playwright test -g "HP-001"

# Solo Happy Path
npx playwright test -g "Happy Path"

# Solo Edge Cases
npx playwright test -g "Edge Cases"
```

### Por Navegador

```bash
# Solo Chrome
npm run test:chromium

# Solo Firefox
npm run test:firefox

# Versión móvil
npm run test:mobile
```

## 🎯 Casos de Uso Comunes

### Quiero Probar la Funcionalidad del Carrito

```bash
npx playwright test -g "carrito|cart"
```

### Quiero Ver Si el Sitio Funciona en Mobile

```bash
npm run test:mobile
```

### Quiero Generar Nuevos Tests

```bash
npm run codegen
# Se abrirá el navegador, navega y Playwright generará el código
```

### Quiero Ver el Reporte de la Última Ejecución

```bash
npm run report
```

## 🐛 Debugging

### Ver test paso a paso

```bash
npm run test:debug
```

### Ver screenshots de fallos

```bash
# Los screenshots están en: ./screenshots/
# Los videos están en: ./test-results/
```

### Ver trazas detalladas

```bash
# Después de ejecutar tests, ver la traza:
npx playwright show-trace test-results/[nombre-del-test]/trace.zip
```

## 📈 Análisis de Resultados

### Ver reporte HTML completo

```bash
npm run report
```

### Ver solo tests fallidos

```bash
npx playwright test --reporter=list
```

### Generar reporte JSON

```bash
npx playwright test --reporter=json > test-results.json
```

## 🔧 Configuración Personalizada

### Cambiar timeout global

Edita `playwright.config.js`:

```javascript
use: {
  actionTimeout: 30000, // 30 segundos
}
```

### Ejecutar en paralelo

```bash
npx playwright test --workers=4
```

### Ejecutar secuencialmente

```bash
npx playwright test --workers=1
```

## 📝 Estructura de un Test

```javascript
test('Nombre descriptivo del test', async ({ page }) => {
  // 1. Navegar
  await page.goto('/');
  
  // 2. Interactuar
  await page.click('button');
  await page.fill('input', 'texto');
  
  // 3. Verificar (Assertions)
  await expect(page.locator('h1')).toBeVisible();
  await expect(page).toHaveURL(/expected-url/);
  
  // 4. Screenshot (opcional)
  await page.screenshot({ path: 'screenshot.png' });
});
```

## 🎨 Selectores Útiles

```javascript
// Por texto
page.locator('text=Pizza')

// Por role
page.locator('role=button[name="Agregar"]')

// Por data-testid
page.locator('[data-testid="cart-button"]')

// CSS selector
page.locator('.cart-icon')

// Combinado
page.locator('button:has-text("Agregar")')
```

## ⚠️ Troubleshooting

### Error: "Browser not installed"

```bash
npx playwright install chromium
```

### Error: "Timeout exceeded"

- Aumenta el timeout en playwright.config.js
- O usa esperas explícitas: `await page.waitForSelector()`

### Tests fallan aleatoriamente

- Agrega `await page.waitForLoadState('networkidle')`
- Usa selectores más estables
- Aumenta timeouts

### No se generan screenshots

- Verifica que la carpeta `screenshots/` exista
- Revisa permisos de escritura

## 📚 Recursos

- [Playwright Docs](https://playwright.dev)
- [Selectores](https://playwright.dev/docs/selectors)
- [Assertions](https://playwright.dev/docs/test-assertions)
- [API Reference](https://playwright.dev/docs/api/class-playwright)

## 💡 Tips

1. **Usa el UI Mode** para desarrollo: `npm run test:ui`
2. **Usa codegen** para generar selectores: `npm run codegen`
3. **Captura screenshots** en puntos clave
4. **Usa data-testid** para selectores estables
5. **Mantén tests independientes** (no dependan entre sí)
6. **Limpia el estado** después de cada test

---

**¿Necesitas ayuda?** Consulta el README.md completo o la documentación oficial de Playwright.

