# Check! — Asistente Digital (Proyecto estático)

Proyecto front-end estático llamado **Check!**: un asistente digital minimalista que conecta modos para estudiantes, ciudadanos y empresas, permitiendo crear y gestionar tareas/localmente usando `localStorage`.

**Estado:** Prototipo / interfaz estática (sin backend)

## Características principales

- **Gestión de tareas:** Añadir, listar y eliminar tareas (modo Estudiante).  
- **Validaciones:** Fecha no anterior a hoy y detección de duplicados.  
- **UI responsiva:** Formulario se muestra en modal en móvil y en panel en escritorio.  
- **Almacenamiento local:** Usa `localStorage` (clave configurable por página con el atributo `data-storage`).

## Estructura del proyecto

- **`index.html`**: Página de inicio con navegación a los modos.  
- **`estudiante.html`**, **`ciudadano.html`**, **`empresa.html`**: Vistas por tipo de usuario.  
- **`script.js`**: Lógica JS para añadir/eliminar tareas, validaciones y renderizado.  
- **`style.css`**, **`eststyle.css`**, **`empstyle.css`**: Estilos principales por página.  
- **`imagenes/`**: Recursos gráficos (logos, favicons, etc.).  
- **`LICENSE`**: Licencia del proyecto.

## Detalles técnicos relevantes

- El `body` en las páginas puede incluir `data-storage="tasks_estudiante"` para definir la clave usada en `localStorage`. Si no existe, el script usa `tasks_default`.
- Validaciones importantes en `script.js`:
  - `isFutureDate`: impide fechas pasadas.  
  - `isDuplicate`: evita tareas con mismo título/clase/fecha.  
- El formulario se mueve dinámicamente entre el modal (`#formModal`) y el contenedor de escritorio `.task-form-desktop` según `matchMedia("(min-width:768px)")`.

## Cómo ejecutar (local, rápido)

Opciones sencillas para probar el proyecto en tu máquina:

- Abrir directamente el archivo (Windows PowerShell):

```powershell
start .\index.html
```

- Servir desde un servidor estático (recomendado para evitar limitaciones de rutas):

```powershell
python -m http.server 8000
# luego abrir http://localhost:8000 en el navegador
```

No hay dependencias externas de node/paquetes; es una app front-end estática.

## Cómo contribuir

- Abrir un issue con cambios propuestos o enviar un pull request.  
- Si añades funcionalidades JS, por favor mantén la compatibilidad con navegadores modernos y agrega notas en el README sobre nuevas APIs usadas.

## Ideas / Próximos pasos sugeridos

- Añadir persistencia en servidor (API) para multi-dispositivo.  
- Internacionalización (i18n) si se desea soportar más idiomas.  
- Tests automatizados (unitarios) para las funciones de validación en `script.js`.

## Licencia

El proyecto incluye el archivo `LICENSE` en el repositorio.

---

Archivo agregado: `README.md`.
