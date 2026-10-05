# SquatMotion AI - Análisis Biomecánico

Interfaz web pública para la evaluación cinemática en tiempo real del gesto motor de sentadilla (*squat*), desarrollada mediante visión por computador y segmentación cromática en espacio de color HSV.

## 📌 Descripción del Proyecto
Esta aplicación permite analizar la ejecución de una sentadilla a partir de un video previamente grabado. A través del procesamiento cuadro a cuadro en el navegador, el sistema detecta tres marcadores cromáticos situados en la articulación de la cadera, rodilla y tobillo, calculando de manera automatizada:
- El **ángulo de flexión/extensión de la rodilla** ($\theta$) en grados.
- La **fase del movimiento** (Extendido, Bajando, Flexión Máxima, Subiendo).
- El **conteo de repeticiones válidas** según el umbral biomecánico configurado.
- Los valores de **Flexión Máxima** ($\theta_{\min}$) y **Extensión Máxima** ($\theta_{\max}$).
- La **graficación temporal** de la trayectoria del ángulo articular.

---

## 🚀 Requisitos y Dependencias

No se requiere la instalación de software ni servidores locales. Toda la lógica se ejecuta del lado del cliente (*Client-Side JavaScript*).

### Requisitos del Sistema
- **Navegador web moderno:** Google Chrome, Microsoft Edge, Mozilla Firefox o Safari.
- Conexión a Internet (únicamente para la carga inicial de las librerías vía CDN).

### Librerías e Integraciones (vía CDN)
- **[Tailwind CSS](https://tailwindcss.com/):** Estilizado de la interfaz y diseño responsivo.
- **[Chart.js](https://www.chartjs.org/):** Renderizado de la gráfica de evolución del ángulo en tiempo real.
- **[FontAwesome](https://fontawesome.com/):** Iconografía de la interfaz.

---

## 🛠️ Instrucciones de Uso

1. **Cargar el Video:** Haz clic en el botón `Seleccionar Video` y sube un archivo en formato `.mp4` con la toma lateral del sujeto.
2. **Configurar el Color del Marcador:** En el panel de control inferior, selecciona el color de los marcadores físicos empleados (por defecto: *Verde Neón*).
3. **Calibrar Sensibilidad y Umbral:**
   - **Sensibilidad Color:** Ajusta la tolerancia del filtro HSV en caso de que las condiciones de iluminación varíen.
   - **Umbral Sentadilla:** Ajusta el límite angular (por defecto: $90^\circ$) para considerar válida una repetición.
4. **Iniciar Análisis:** Presiona el botón `Iniciar`. El video comenzará a reproducirse superponiendo el esqueleto cinemático y actualizando los indicadores en vivo.
5. **Reiniciar Métricas:** Utiliza el botón de reinicio para limpiar el historial de repeticiones y la gráfica si deseas evaluar un nuevo intento.
