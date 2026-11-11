# ⚡ Newton-Raphson: Root Slayer (DOOM Edition)

> **Laboratorio Didáctico e Interactivo de Métodos Numéricos para Ingeniería**  
> Explicación visual, paso a paso y táctica del Método de Newton-Raphson para el cálculo de raíces de ecuaciones no lineales con estética y "game feel" retro inspirados en **DOOM (1993)**.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Bootstrap 5](https://img.shields.io/badge/Bootstrap_5-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly.js-3F4F75?style=for-the-badge&logo=plotly&logoColor=white)
![KaTeX](https://img.shields.io/badge/KaTeX-007ACC?style=for-the-badge&logo=latex&logoColor=white)
![Math.js](https://img.shields.io/badge/Math.js-212121?style=for-the-badge)

---

## 🎮 Características Destacadas

### 🎯 1. Núcleo Visual & Arena Gráfica Interactiva (Plotly.js)
- **Click-to-Aim táctico:** Haz clic directamente sobre la curva $f(x)$ para apuntar y calibrar el punto de arranque $x_0$ de forma interactiva e intuitiva.
- **Trazado semántico de tangentes:**
  - 🔵 **Azul Plasma:** Curva de la función continua principal $y = f(x)$.
  - 🔥 **Fuego / Naranja Sangre:** Recta tangente en el punto $(x_n, f(x_n))$ proyectada hasta el eje $X$.
  - 🟡 **Amarillo Neón:** Proyección vertical punteada desde el corte $(x_{n+1}, 0)$ hasta $(x_{n+1}, f(x_{n+1}))$ preparando el siguiente disparo.
  - 🟢 **Verde Radioactivo:** Marcador cruzado cuando el residuo cumple la tolerancia prefijada (*Raíz Slayed*).

### 📐 2. Rigor Académico & Métodos Numéricos
- **Fórmula viva con KaTeX:** Reemplazo paso a paso de los valores evaluados en tiempo real:
  $$x_{n+1} = x_n - \frac{f(x_n)}{f'(x_n)}$$
- **Monitor de Convergencia Cuadrática $O(h^2)$:** Muestra en tiempo real cómo los dígitos de precisión se duplican en cada iteración (`+1 dec`, `+3 dec`, `+7 dec`, `+14 dec`), demostrando visualmente el teorema fundamental del método.
- **Exportador a LaTeX con un solo clic:** Botón `[COPIAR LATEX]` que copia la tabla de iteraciones en sintaxis `\begin{table}\begin{tabular}...` lista para pegar directamente en informes universitarios o papers.
- **Casos de Falla y Detección de $f'(x) \approx 0$:** Si la derivada se anula (recta tangente horizontal), el sistema detiene la animación y abre un modal didáctico explicando por qué se produce la división por cero e indetermina la recurrencia.

### 🕹️ 3. Estética Auténtica DOOM & Inmersión Retro
- **Dashboard Zero-Scroll (`100vh` estricto):** Todo el sistema cabe perfectamente en la pantalla sin scroll vertical en el navegador.
- **HUD Inferior Clásico:** Indicadores tipo arcade militar (Iteración, Precisión, Cifras exactas, Estimado de raíz, Estado de convergencia).
- **Doomguy Reactivo:** Su estado de ánimo cambia de *Listo* a *Herido/Dañado* en divergencias y a *God Mode* (ojos brillantes) al aniquilar la raíz.
- **Micro-Retroceso & Flash Cinético:** Sensación de disparo táctil al presionar cada paso (`firing-kick` & `firing-flash`).
- **Efectos de Audio 8-bit:** Sintetizados puramente con la API nativa de Web Audio (sin dependencias de archivos de sonido externos).

---

## 🔬 Fundamento Teórico

El método de **Newton-Raphson** es un algoritmo iterativo de orden abierto derivado de la serie de Taylor truncada de primer orden:

$$f(x_{n+1}) \approx f(x_n) + f'(x_n)(x_{n+1} - x_n) = 0$$

Despejando algebraicamente el corte con el eje horizontal:

$$x_{n+1} = x_n - \frac{f(x_n)}{f'(x_n)}$$

El error relativo porcentual se calcula como:

$$\text{Error } \% = \left| \frac{x_{n+1} - x_n}{x_{n+1}} \right| \times 100$$

---

## 🚀 Cómo Ejecutar el Proyecto

Este proyecto es un **archivo único autónomo** (`index.html`), por lo que no requiere compilación, `npm install` ni servidores pesados:

### Opción 1: Abrir directamente
Haz doble clic sobre el archivo `index.html` o ábrelo con cualquier navegador moderno (Chrome, Firefox, Edge, Safari, Brave).

### Opción 2: Servidor local rápido (Python)
```bash
# Clona el repositorio
git clone https://github.com/Eucamilinho/newton-raphson-doom.git
cd newton-raphson-doom

# Inicia un servidor HTTP ligero
python3 -m http.server 8080
```
Luego abre tu navegador en `http://localhost:8080`.

---

## 🛠️ Tecnologías y Librerías Utilizadas

- **HTML5 & CSS3 nativo:** Dashboard responsivo con flexbox/grid, variables CSS, CRT scanlines y microanimaciones de disparo.
- **Bootstrap 5:** Sistema base de rejilla y utilidades.
- **Plotly.js (v2.32.0):** Trazado dinámico de curvas matemáticas, vectores y eventos `plotly_click`.
- **Math.js (v12.4.1):** Parseo algebraico, compilación y diferenciación simbólica automática (`math.derivative`).
- **KaTeX (v0.16.9):** Renderizado tipográfico ultrarrápido de fórmulas matemáticas.
- **Web Audio API:** Sintetizador sonoro analógico de 8 bits sin dependencias externas.

---

## 📜 Licencia

Distribuido bajo la Licencia **MIT**. Puedes usarlo, modificarlo y compartirlo libremente con fines educativos y académicos.
