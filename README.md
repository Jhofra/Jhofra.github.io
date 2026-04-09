# Gastos del Mes (Web + Android APK)

Aplicación de control de gastos personales por categoría, con soporte de registro manual y por voz.

## Funcionalidades

- Título principal: **GASTOS DEL MES**
- Estado vacío: **No hay ningún control de dinero**
- Crear categorías con:
  - nombre
  - gasto máximo
- Registrar gastos con:
  - monto
  - categoría seleccionable
- Borrar ítems:
  - eliminar categoría completa (con todos sus gastos)
  - eliminar gastos individuales por categoría
- Registro por voz con frases como:
  - `Gastar 20 en comida`
  - `Registrar 15 soles en transporte`
- Cálculo de:
  - presupuesto
  - gastado
  - restante
  - porcentaje
- Barra de progreso proporcional
- Persistencia local con `localStorage`
- Moneda por defecto: **S/** (PEN)
- Diseño moderno, responsive y minimalista

## Estructura

```text
.
├── index.html
├── src/
│   └── app.js
├── styles/
│   └── main.css
├── capacitor.config.json
└── package.json
```

## Ejecutar como web

### Opción 1
Abrir `index.html` directamente en el navegador.

### Opción 2 (recomendada)
```bash
npm install
npm run start
```
Abrir: `http://localhost:5173`

---

## Generar APK Android (Capacitor)

> Requisitos:
> - Node.js 20+
> - Android Studio instalado
> - SDK de Android configurado

1. Instalar dependencias:
```bash
npm install
```

2. Crear plataforma Android (solo la primera vez):
```bash
npm run cap:add:android
```

3. Sincronizar cambios web a Android:
```bash
npm run cap:sync
```

4. Abrir proyecto Android:
```bash
npm run cap:open:android
```

5. En Android Studio:
   - `Build > Build Bundle(s) / APK(s) > Build APK(s)`
   - Se generará el APK en la ruta que Android Studio indique.

## Nota sobre reconocimiento de voz en Android

- El reconocimiento usa `SpeechRecognition` del WebView/navegador.
- Dependiendo de versión de Android/WebView, puede requerir permisos de micrófono y conectividad.
- Si un dispositivo no soporta reconocimiento de voz web, el registro manual sigue funcionando.

## Resolución de conflictos (PR)

Si GitHub muestra conflictos en `README.md`, `src/app.js` o `styles/main.css`, esta rama ya deja la versión unificada con:

- flujo de gastos por voz y persistencia,
- borrado de categorías y gastos individuales,
- estilos responsive sin bloques duplicados ni marcadores de merge (`<<<<<<<`, `=======`, `>>>>>>>`).
