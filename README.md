# STOREXGAMER PKG — GitHub Pages + Hana

Paquete completo para reemplazar el `index.html` de STOREXGAMER PKG y, opcionalmente, activar el backend de Hana.

## Contenido

- `index.html`: diseño HANA NEON, responsive, catálogo, buscador, filtros, Admin, chat escrito y dictado por micrófono.
- Hana puede anunciar altas de juegos y aplicaciones con «¡Hay actualización gamer!».
- Sincronización del catálogo para todos los visitantes usando el Worker y KV.
- `worker/worker.js`: API separada para chat IA, diseño de la voz original, selección de la voz, audio TTS y catálogo compartido.
- `worker/wrangler.toml`: binding de Workers AI, KV y origen autorizado de GitHub Pages.
- `INSTRUCCIONES_GITHUB_PAGES.txt`: guía completa en español.

## Publicación

1. Reemplaza el `index.html` de tu repositorio GitHub Pages con el de este paquete.
2. Despliega `worker/worker.js` usando la configuración de `worker/wrangler.toml`.
3. Configura en el Worker los secretos `ELEVENLABS_API_KEY` y `HANA_ADMIN_TOKEN`.
4. Copia la URL base del Worker dentro de `SXG_DEFAULT_WORKER_BASE` en `index.html` y vuelve a publicarlo.
5. En el panel de Hana, configura el token Admin para generar la voz y publicar el catálogo.

GitHub Pages no ejecuta el Worker. El HTML funciona con respuestas locales y voz del navegador mientras el backend no esté conectado. La voz neuronal requiere configurar el proveedor y puede consumir créditos; la configuración de cualquier clave y facturación debe gestionarla un adulto responsable.

## Importante

El login visual del panel Admin es solo una barrera de demostración porque su lógica está dentro del HTML público. La escritura del catálogo compartido se valida aparte con `HANA_ADMIN_TOKEN` en el Worker. No publiques claves ni tokens en el repositorio.
