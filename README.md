# D&P LeadPro

Producto digital de **DP Ingeniería Integral**.
Dominio: **https://leadpro.dpingenieriaintegral.com**

## Estructura

```
public/index.html            ← clon 1:1 (byte a byte) de Demo_D&P_LeadPro_v5.html
vercel.json                  ← sirve /public como sitio estático
Demo_D&P_LeadPro_v5.html     ← ORIGINAL (fuente de verdad, no editar)
```

El HTML original manda: `public/index.html` debe ser idéntico al original.
Verificar con:

```bash
sha256sum "Demo_D&P_LeadPro_v5.html" public/index.html
```

Si se actualiza el original, volver a copiarlo:

```bash
cp "Demo_D&P_LeadPro_v5.html" public/index.html
```

## Publicar en el subdominio (Vercel)

1. `vercel --prod` desde esta carpeta (o conectar el repo en Vercel).
2. En el proyecto de Vercel → Settings → Domains → agregar `leadpro.dpingenieriaintegral.com`.
3. En el DNS de `dpingenieriaintegral.com`, crear el registro:

   | Tipo  | Nombre    | Valor                  |
   |-------|-----------|------------------------|
   | CNAME | `leadpro` | `7936cef18d41b918.vercel-dns-017.com` |

   (El DNS de dpingenieriaintegral.com está en Hostinger: ns1/ns2.dns-parking.com.
   Proyecto Vercel: `dp-leadpro`, equipo DP.)

Es un sitio 100 % estático (sin dependencias externas); funciona en cualquier hosting
(cPanel, Netlify, S3, etc.) subiendo `public/index.html` a la raíz del subdominio.
