# Clima por Ubicación — Proyecto AOS 2.1

Página web que obtiene la ubicación geográfica del usuario (latitud/longitud), consulta **Azure Maps** para el nombre del lugar y **Open-Meteo** para datos climáticos.

## Requisitos cumplidos

| Requisito | Implementación |
|-----------|----------------|
| Ubicación (lat/lon) | Geolocation API del navegador |
| API de Azure | Azure Maps — Reverse Geocoding |
| API de clima | Open-Meteo (temperatura, humedad, condición) |
| Ubicación consultada | Nombre legible vía Azure Maps |

## Configuración de Azure Maps

1. Entra a [Azure Portal](https://portal.azure.com).
2. Crea un recurso **Azure Maps** (nivel gratuito disponible).
3. Ve a **Authentication** y copia la **Primary Key**.
4. Abre `js/config.js` y reemplaza `TU_CLAVE_AZURE_MAPS_AQUI` con tu clave.

```javascript
const CONFIG = {
  AZURE_MAPS_KEY: 'tu-clave-real-aqui',
  // ...
};
```

## Ejecutar localmente

Abre `index.html` en el navegador o usa un servidor local:

```powershell
# Con Python (si está instalado)
python -m http.server 8080

# O con npx
npx serve .
```

Luego visita `http://localhost:8080`.

> **Nota:** La geolocalización requiere HTTPS o `localhost`. El navegador pedirá permiso para acceder a tu ubicación.

## Uso

1. Pulsa **Obtener mi ubicación** para usar el GPS del dispositivo.
2. O ingresa latitud/longitud manualmente y pulsa **Consultar**.

## APIs utilizadas

- **Geolocation API** — [MDN](https://developer.mozilla.org/es/docs/Web/API/Geolocation_API)
- **Azure Maps Reverse Geocoding** — [Documentación](https://learn.microsoft.com/azure/azure-maps/how-to-search-for-address)
- **Open-Meteo** — [Documentación](https://open-meteo.com/en/docs)

## Estructura del proyecto

```
├── index.html
├── css/styles.css
├── js/
│   ├── config.js      ← Tu clave de Azure Maps
│   └── app.js         ← Lógica principal
└── README.md
```
