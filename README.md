# MM Mirna Boutique — Portal de Arquitectura y Documentación Técnica

Centro visual interactivo de casos de uso, arquitectura de software, infraestructura y flujos de negocio para **MM Mirna Boutique E-Commerce**, diseñado especialmente para nuestros socios directores **Julito** y **René**.

Generado con tecnología **[Archify](https://github.com/tt-a1i/archify)**.

---

## 🏛️ Diagramas Interactivos Disponibles

Los diagramas compilados se encuentran en la carpeta `dist/` en formato **HTML completamente autónomo** (no requieren internet ni backend para funcionar una vez descargados):

| # | Diagrama | Tipo | Archivo Compilado | Descripción Clave |
|---|---|---|---|---|
| **01** | **Topología Global del Sistema** | Arquitectura | [`dist/01-global-architecture.html`](dist/01-global-architecture.html) | Visión panorámica completa: Storefront, CMS, Core API, PostgreSQL y SaaS externos. |
| **02** | **Ciclo de Vida de Órdenes (Sales Orders)** | Ciclo de Vida | [`dist/02-sales-orders-lifecycle.html`](dist/02-sales-orders-lifecycle.html) | Estados de la orden (`draft` → `pending` → `paid` → `processing` → `shipped` → `delivered`). Detalla la regla crítica de descuento de stock en Kardex. |
| **03** | **Checkout y Conciliación de Pagos** | Flujo de Trabajo | [`dist/03-checkout-payment-workflow.html`](dist/03-checkout-payment-workflow.html) | Pasos de compra, reporte de referencia bancaria (Pago Móvil / Zelle / Transferencia) y auditoría administrativa en CMS. |
| **04** | **Catálogo, Precios BCV e Inventario Kardex** | Flujo de Trabajo | [`dist/04-catalog-inventory-workflow.html`](dist/04-catalog-inventory-workflow.html) | Carga de prendas, optimización WebP en ImageKit CDN, fijación de precios en USD + 20% REF en Bs (Dolarify) y libro contable Kardex. |
| **05** | **Autenticación y Recuperación de Claves** | Secuencia | [`dist/05-auth-security-sequence.html`](dist/05-auth-security-sequence.html) | Seguridad de contraseñas con Bcrypt, emisión de tokens JWT y recuperación mediante enlaces criptográficos temporales vía Resend. |
| **06** | **Despliegue e Infraestructura Cloud** | Arquitectura | [`dist/06-deployment-infrastructure.html`](dist/06-deployment-infrastructure.html) | Despliegue en Railway Cloud: contenedores Docker, servidor Caddy HTTP/2 para Angular, red privada interna y aislamiento de base de datos. |

---

## 🚀 Cómo Ver la Documentación Localmente

### Opción 1: Directo en el Navegador
Simplemente abre el archivo `dist/index.html` haciendo doble clic desde el Finder / Explorador de archivos en cualquier navegador moderno (Chrome, Safari, Firefox, Edge).

### Opción 2: Servidor Local Rápido
Con Node.js instalado:
```bash
# Con npx
npx serve dist

# O con Python 3
python3 -m http.server 3333 -d dist
```
Luego abre `http://localhost:3333` en tu navegador.

---

## 🌐 Publicación Online para Acceso Continuo de Socios

La carpeta `dist/` es un sitio estático 100% independiente. Puede alojarse en:
- **GitHub Pages**: Configurando la rama a la carpeta `dist/`.
- **Vercel / Netlify**: Conectando este repositorio y configurando `dist` como "Output Directory".
- **Railway**: Creando un servicio estático apuntando a este repositorio.

---

## 🛠️ Modificación y Recompilación de Diagramas

Los archivos fuente de cada diagrama son especificaciones JSON declarativas ubicadas en `diagrams/`:
- `diagrams/01-global-architecture.json`
- `diagrams/02-sales-orders-lifecycle.json`
- `diagrams/03-checkout-payment-workflow.json`
- `diagrams/04-catalog-inventory-workflow.json`
- `diagrams/05-auth-security-sequence.json`
- `diagrams/06-deployment-infrastructure.json`

Para recompilar todos los diagramas tras hacer cambios:
```bash
npm run build
```
O compilar uno específico:
```bash
npm run render:01
npm run render:02
npm run render:03
npm run render:04
npm run render:05
npm run render:06
```

---

## 💎 Características Interactivas del Motor Archify
- **Zoom & Pan:** Arrastra con el ratón o usa la rueda para explorar áreas complejas.
- **Modo Animación (Trace):** Visualiza los flujos de paquetes y peticiones en movimiento.
- **Inspector de Nodos:** Haz clic en cualquier componente o estado para ver detalles técnicos y notas de auditoría.
- **Temas:** Alterna al instante entre tema oscuro y tema claro en la esquina superior.
