---
title: "Taller de Inteligencia Artificial"
subtitle: "Clase 00 - Introducción"
theme: seriph
background: https://images.unsplash.com/photo-1550745165-9bc0b252726f?q=80&w=4140&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
class: text-center
transition: slide-left
info: |
  **Modalidad práctica sobre Agentes Inteligentes**

  Basado en el libro *Sutton y Barto*
addons:
  - slidev-addon-python-runner

# Optional configuration for this runner
python:
  # Install packages from PyPI. Default: []
  installs: ["gymnasium"]

  # Code executed to set up the environment. Default: ""
  prelude: |
    GREETING_FROM_PRELUDE = "Hello, Slidev!"

  # Automatically load the imported builtin packages. Default: true
  loadPackagesFromImports: true

  # Disable annoying warning from `pandas`. Default: true
  suppressDeprecationWarnings: true

  # Always reload the Python environment when the code changes. Default: false
  alwaysReload: false

  # Options passed to `loadPyodide`. Default: {}
  loadPyodideOptions: {}
---

# Taller de Inteligencia Artificial

---

# Presentación del Curso

<v-clicks>

- **Agentes Inteligentes (parte práctica) 🤖:**
  Exploraremos y desarrollaremos soluciones basadas en IA utilizando aprendizaje por refuerzo con librerías como [gymnasium](https://gymnasium.farama.org/index.html).

- **Basado en Sutton y Barto 📓:**
  Este libro es la referencia teórica para entender el comportamiento y la toma de decisiones de los agentes. Usaremos algunos de sus ejemplos para implementar en Python.

- **Modalidad práctica 💻:**
  Cada clase se inicia con una consigna o exposición de alguna librería/herramienta, seguida de ejercicios que deben desarrollarse en grupo o individualmente (máximo 3 alumnos).
  > Los ejercicios pueden continuarse en casa y se presentarán en fechas estipuladas.

</v-clicks>

---

# Puntos del Curso

<div grid="~ cols-2 gap-8">
  
**Obligatorio (50 puntos)**

- Entrega final del semestre por [Gestión ORT](https://gestion.ort.edu.uy/) (online)
- Fecha estipulada en [Gestión ORT](https://gestion.ort.edu.uy/)
- **Defensa:** escrita durante el parcial y posiblemente oral (coordinada por Teams días después del parcial)

**Laboratorios (30 puntos)**

- Entrega online por [Aulas ORT](https://aulas.ort.edu.uy/)
- Fechas se estipularán en clase

**Parcial (20 puntos)**

- Al terminar las clases. Presencial, individual y escrito.
- Revisar fecha en [Gestión ORT](https://gestion.ort.edu.uy/)

</div>

---
layout: two-cols
---

## Prerequisitos Técnicos

<br>

- **Python Básico 🐍:**  
  Manejar estructuras de control (_if_, _for_, etc.) y comprender fragmentos de código.
- **Uso de Librerías 📚:**  
  Familiarizarse con la instalación y utilización de paquetes, sin memorizar cada detalle.
- **Fundamento Teórico 📓:**  
  Las clases se apoyan en bases teóricas; la bibliografía es el pilar para aplicar lo práctico.

::right::

## Buenas Prácticas

<br>

- **Entender sobre Memorizar 🧠:**  
  La clave es comprender el propósito de cada bloque.  
  Consulta la documentación y explora constantemente.
- **Curiosidad como Motor 🤔:**  
  La inquietud y el cuestionamiento te ayudarán a profundizar y a encontrar soluciones.
- **Uso Inteligente de la IA 🤖:**  
  La IA es una herramienta de apoyo. Asegúrate de balancear su ayuda con investigación personal.

---
layout: cover 
background: https://images.unsplash.com/photo-1523039031846-6b3f39302cb8?q=80&w=1920
---

# Setup del ambiente

---

# Setup del ambiente: Dónde Correr el Código?

<br>
<div grid="~ cols-3 gap-8">

  <div v-click>
    <h3>Google Colab ☁️</h3>
    <ul>
      <li><strong>Ventajas:</strong> Listo para usar (free tier ok).</li>
      <li><strong>Desventajas:</strong> Sesiones interrumpidas, manejo limitado de archivos.</li>
      <li><strong>Para:</strong> Usuarios que buscan facilidad.</li>
      <li><a href="https://colab.research.google.com/">Link</a> </li>
    </ul>
  </div>

  <div v-click>
    <h3>Laboratorios ORT 🏫</h3>
    <ul>
      <li><strong>Ventajas:</strong> Ambiente preconfigurado, acceso a GPU.</li>
      <li><strong>Desventajas:</strong> Recursos limitados en horas pico.</li>
      <li><strong>Para:</strong> Uso remoto de GPU sin costo extra.</li>
      <li><a href="https://notebook-id.facultades.ort.edu.uy/">Link</a> </li>
    </ul>
  </div>

  <div v-click>
    <h3>Local 💻</h3>
    <ul>
      <li><strong>Ventajas:</strong> Total control y flexibilidad.</li>
      <li><strong>Desventajas:</strong> Requiere configuración (uso de conda/venv).</li>
      <li><strong>Para:</strong> Usuarios técnicos con buena GPU o MPS (Mac).</li>
    </ul>
  </div>

</div>

<div class="mt-8" v-click>
  <p><em>Nota:</em> Para tareas en CPU, cualquiera de estas opciones es válida.</p>
</div>

---
layout: image-right
image: https://miro.medium.com/v2/resize:fit:640/format:webp/0*X6sHaKrSQBeZfsi_.png
---


# Setup local
Usar nuestra computadora

1. **Instalar Python**  
2. **Crear un entorno virtual**  
3. **Instalar dependencias clave**  
4. **Verificar instalación**  

<br>
<img v-click src="https://www.dataquest.io/wp-content/uploads/2022/01/python-virtual-envs1-1024x576.webp" class="mx-auto block" alt="Python Virtual Environment" />
---
layout: two-cols
---

# Instalar Python y crear un entorno con Conda

- **¿Por qué usar ambientes?**

  - Aíslan dependencias y evitan conflictos.
  - Recomendación: un ambiente por materia/proyecto.

- **Usaremos Miniconda:**
  - Descarga: [Miniconda](https://docs.anaconda.com/miniconda/)
  - Guía de instalación: [Instalar Miniconda](https://docs.anaconda.com/miniconda/install)

::right::

<div class="flex items-center justify-center h-full">
  <img src="https://www.anaconda.com/wp-content/uploads/2024/11/2020_Anaconda_Logo_RGB_Corporate.png" class="mx-auto block" alt="Anaconda Logo"/>
</div>
---
layout: two-cols
---

# Crear y Verificar tu Ambiente Conda

1. **Crear el ambiente desde el repositorio:**

```bash
conda env create -f https://raw.githubusercontent.com/Catedra-IA/taller-inteligencia-artificial-ambiente/main/environment.yml
```

2. **Activar el ambiente:**

```bash
conda activate taller-ia
```

3. **(opcional) Verificar la instalación:**

```bash
curl -O https://raw.githubusercontent.com/Catedra-IA/taller-inteligencia-artificial-ambiente/main/verificar_instalacion.py
python verificar_instalacion.py
```

<br>

> El script verifica todas las dependencias necesarias para cada clase del curso.

<a href="https://github.com/Catedra-IA/taller-inteligencia-artificial-ambiente" class="text-sm">github.com/Catedra-IA/taller-inteligencia-artificial-ambiente</a>

::right::

<div class="flex flex-col items-center justify-center h-full gap-4">
  <img src="https://www.anaconda.com/wp-content/uploads/2024/11/2020_Anaconda_Logo_RGB_Corporate.png" class="mx-auto block" alt="Anaconda Logo"/>
</div>
---
layout: two-cols
---

# Notebooks

- **Interactividad:**  
  Ejecutar y modificar código en tiempo real.
- **Contar una historia:**  
  Comentarios que explican cada paso y conclusiones.
- **Perfecto para Investigaciones y aprendizaje:**  
  Experimentar, documentar y compartir resultados fácilmente.

::right::

```markdown
# Historia de un Experimento:
Exploramos la relación entre un ángulo y su función seno.
```

```python
import numpy as np
import matplotlib.pyplot as plt
```

```python
# Generamos 100 puntos entre 0 y 2π
x = np.linspace(0, 2 * np.pi, 100)
# Calculamos el seno de x
y = np.sin(x)
```

```python
# Visualizamos la función
plt.figure(figsize=(8, 4))
plt.plot(x, y, color='blue', label='y = sin(x)')
plt.title("Explorando la Función Seno")
plt.xlabel("Ángulo (radianes)")
plt.ylabel("Valor de sin(x)")
plt.legend()
plt.show()
```

```markdown
# Conclusión:
La gráfica revela la periodicidad de la función seno,
```

---
layout: two-cols
---

# Notebooks
cloud vs local

**Opciones Cloud**
- Instancias gestionadas automáticamente.
- No necesitas instalar herramientas.
- Ideal para comenzar rápido.

**Uso Local**
- Requiere instalar `jupyter notebook`.
- Ejecutable desde el navegador o integrado en [VS Code](https://code.visualstudio.com/).

::right::

<div class="flex items-center justify-center h-full">
  <img src="https://jupyter.org/assets/homepage/main-logo.svg" alt="Jupyter Notebook" class="w-64 mx-auto block" />
</div>
---

# Instalación Jupyter Notebook
Solo local⚠️

Para quienes prefieren trabajar localmente, instalar el paquete:

```bash
conda install -c conda-forge jupyter
```

Luego, iniciar el entorno Notebook con:

```bash
jupyter notebook
```
<br>

### Notas
- Una vez terminada la instancia, se pierde la sesión.
- Visual Studio Code y otros IDEs ofrecen integración con notebooks.
---
layout: cover
background: https://images.unsplash.com/photo-1558611848-73f7eb4001a1?q=80&w=3500&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
---

# Gymnasium

---
layout: two-cols
---

# Gymnasium
Introducción 

**Framework para RL**  
Evolución de [OpenAI Gym](https://www.gymlibrary.dev/index.html), diseñado para simular entornos de aprendizaje por refuerzo.

**Interfaz Simple y Estandarizada**  
Ejecuta acciones, recibe estados (observaciones) y recompensas de manera consistente.

**Amplia Variedad de Entornos**  
Desde tareas clásicas hasta simulaciones complejas, ideales para experimentar.

::right::
<div class="flex items-center justify-center h-full">
  <img src="https://gymnasium.farama.org/_images/lunar_lander.gif" alt="Gymnasium Logo" class=""/>
</div>

---

# ¿Qué se puede hacer con Gymnasium?

<div grid="~ cols-4 gap-4">

<div class="text-center">
  <img src="https://gymnasium.farama.org/_images/cart_pole.gif" class="h-30 mx-auto" alt="CartPole"/>
  <p class="text-sm mt-2"><strong>CartPole</strong><br>Equilibrar un palo</p>
</div>

<div class="text-center">
  <img src="https://gymnasium.farama.org/_images/mountain_car.gif" class="h-30 mx-auto" alt="MountainCar"/>
  <p class="text-sm mt-2"><strong>MountainCar</strong><br>Subir la montaña</p>
</div>

<div class="text-center">
  <img src="https://gymnasium.farama.org/_images/lunar_lander.gif" class="h-30 mx-auto" alt="LunarLander"/>
  <p class="text-sm mt-2"><strong>LunarLander</strong><br>Aterrizar en la luna</p>
</div>

<div class="text-center">
  <img src="https://gymnasium.farama.org/_images/taxi.gif" class="h-30 mx-auto" alt="Taxi"/>
  <p class="text-sm mt-2"><strong>Taxi</strong><br>Llevar pasajeros</p>
</div>

</div>

<br>

<div v-click class="text-center">

Todos estos entornos comparten la **misma interfaz**: <span v-mark.underline.blue>`reset()`</span>, <span v-mark.underline.orange>`step(action)`</span>, <span v-mark.underline.red>`close()`</span>

</div>

---
layout: two-cols
---

# Interacción en Gymnasium
¿Cómo funciona?

Gymnasium sigue el **paradigma de Agente-Entorno** en aprendizaje por refuerzo:

<v-clicks>

1. **El agente** (una política) <span v-mark.underline.orange>observa</span> el entorno.
2. **Ejecuta una** <span v-mark.underline.orange>acción</span> en base a su política.
3. **El entorno responde**, proporcionando:
   - **Observación** (nuevo "estado" del entorno).
   - **Recompensa** (feedback sobre el desempeño).
   - Otros: terminated, truncated, info.
4. **El ciclo se repite** hasta completar el episodio u otro criterio.

</v-clicks>

::right::

<div class="flex items-center justify-center h-full">
  <LightOrDark>
    <template #dark="props">
      <img src="https://gymnasium.farama.org/_images/AE_loop_dark.png" v-bind="props"/>
    </template>
    <template #light="props">
      <img src="https://gymnasium.farama.org/_images/AE_loop.png" v-bind="props"/>
    </template>
  </LightOrDark>
</div>

---

## Implementación en Python 🐍

Ejemplo básico de interacción con un entorno en Gymnasium:

```python {all|1|3|4|6|7-11|7|8|9|11|7-11|13|all}{lines:true}
import gymnasium as gym

env = gym.make("LunarLander-v3", render_mode="human")
observation, info = env.reset()

episode_over = False
while not episode_over:
    action = env.action_space.sample()  # agent policy that uses the observation and info
    observation, reward, terminated, truncated, info = env.step(action)

    episode_over = terminated or truncated

env.close()
```


<div class="flex items-center justify-center ">
  <LightOrDark width="" alt="">
    <template #dark="props">
      <img src="https://gymnasium.farama.org/_images/AE_loop_dark.png" class="h-40" v-bind="props"/>
    </template>
    <template #light="props">
      <img src="https://gymnasium.farama.org/_images/AE_loop.png" class="h-40" v-bind="props"/>
    </template>
  </LightOrDark>
</div>

---

# Espacios de Acciones y Observaciones en Gymnasium
Limitaciones y posibilidades

- **Espacio de Observación (`observation_space`):**  
  Conjunto de todas las posibles observaciones que el entorno puede proporcionar al agente.

- **Espacio de Acción (`action_space`):**  
  Conjunto de todas las acciones posibles que el agente puede ejecutar en el entorno.

**Tipos Comunes de Espacios:**

- <span v-mark.box.blue>**Box:**</span>  Espacio n-dimensional de valores continuos dentro de límites específicos.

- <span v-mark.box.orange>**Discrete:**</span>  Conjunto finito de acciones posibles, numeradas de 0 a n-1.

<div style="position: absolute; bottom: 10px; width: 100%;">
  <a href="https://gymnasium.farama.org/api/spaces/">Documentación: Gymnasium Spaces</a>
</div>
---
layout: iframe-right

# the web page source
url: https://gymnasium.farama.org/environments/classic_control/cart_pole/
---


```py {monaco-run}
import gymnasium as gym

env = gym.make("CartPole-v1")

print("obs space:", env.observation_space)
print("act space:", env.action_space)

obs, info = env.reset()

print("initial obs:", obs)  
```

<div style="position: absolute; bottom: 10px; width: 100%;">
  <a href="https://jeffjar.me/cartpole.html">Jugar online</a>
</div>

---

# Entornos Disponibles en Gymnasium

Gymnasium ofrece una gran variedad de entornos organizados por categorías:

<div grid="~ cols-3 gap-6">

<div>

**Classic Control**
- CartPole, MountainCar, Pendulum, Acrobot
- Ideales para comenzar

</div>

<div>

**Toy Text**
- FrozenLake, Taxi, Blackjack, CliffWalking
- Problemas discretos simples

</div>

<div>

**Box2D**
- LunarLander, BipedalWalker, CarRacing
- Simulaciones con física 2D

</div>

</div>

<br>

<div v-click>

Explorar más: [gymnasium.farama.org/environments](https://gymnasium.farama.org/environments/classic_control/)

> Además se pueden crear **entornos custom** siguiendo la interfaz de Gymnasium — lo haremos en clase con K-Bandits.

</div>

---

# Temario del Semestre

<div grid="~ cols-2 gap-8">

<div>

| # | Tema |
|---|------|
| 01 | Bandidos de K Brazos |
| 02 | Programación Dinámica |
| 03 | Métodos Monte Carlo |
| 04 | Métodos de Diferencias Temporales |
| 05 | Introducción a PyTorch y Redes Neuronales |

</div>

<div>

| # | Tema |
|---|------|
| 06 | Planificación Dyna-Q |
| 07 | N-Step Bootstrapping |
| 08 | Actor Critic |
| 09 | Stable Baselines |

</div>

</div>

---

# Próxima Actividad: Trabajando con K-Bandits 🎰

En la siguiente sesión, exploraremos el problema de los **K-Bandits** mediante un notebook interactivo.

**Preguntas clave:**
- ¿Cuáles son las <span v-mark.underline.orange>**acciones**</span> disponibles para el agente en este contexto?
- ¿Cómo decide el agente qué acción tomar?
- ¿Qué información nos da la <span v-mark.underline.orange>**recompensa**</span> y cómo la aprovechamos?

---
layout: center
---

# A codificar! 
