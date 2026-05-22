# DinoDash - 2D Endless Runner en Python

![Gameplay de DinoDash](./media/graficos/gameplay.gif)

DinoDash es un videojuego 2D de plataformas desarrollado íntegramente en Python utilizando el framework Pygame. Este proyecto sirve como aplicación práctica de conceptos fundamentales de ingeniería de software, incluyendo Programación Orientada a Objetos (POO), manejo de eventos, detección de colisiones y persistencia de datos.

📄 **[Leer el Manual de Usuario (PDF)](./docs/Manual_Usuario_DinoDash.pdf)**

---

## 💻 Características Técnicas Destacadas

- **Generación Procedimental**: Algoritmo de creación dinámica de plataformas en tiempo real, variando de forma aleatoria la anchura y la distancia entre ellas para escalar la dificultad del juego.

- **Sistema de Físicas y Colisiones**: Implementación de lógicas matemáticas para calcular con precisión la longitud de los puentes generados por el usuario y verificar la intersección con las plataformas destino.

- **Gestión de Estados**: Control fluido del flujo del programa mediante máquinas de estados sencillas (menú principal, gameplay, animaciones del personaje y pantalla de Game Over).

- **Persistencia de Datos**: Sistema de guardado y lectura de la máxima puntuación local utilizando archivos JSON (estadisticas.json), asegurando la persistencia de la información entre diferentes sesiones de juego.

- **Gestión Multimedia**: Integración y control de sprites, animaciones por frames, tipografías personalizadas y canales de audio concurrentes (música de fondo y efectos de sonido reactivos).

---

## Mecánicas de Juego

El objetivo consiste en avanzar a través de plataformas generadas dinámicamente. El jugador debe mantener presionada la barra espaciadora para calcular y construir un puente de longitud exacta que conecte su posición con la siguiente plataforma. 

- **Puntuación y Precisión**: El sistema otorga puntos base por cada transición exitosa y aplica bonificaciones (x2) al calcular con alta precisión el centro de la plataforma destino. 

- **Curva de Dificultad**: La velocidad de escalado del puente y la distancia entre plataformas aumentan progresivamente en función de la puntuación actual. 

---

## 🎮 Interfaz y Controles (UI/UX)

El diseño de la interfaz y la gestión de eventos de entrada (inputs) se han implementado buscando una experiencia de usuario fluida e intuitiva:

- **Controles Core**:
    - `Barra Espaciadora`: Controla la mecánica principal del juego; la longitud del puente es directamente proporcional al tiempo que la tecla se mantiene presionada.  
    - `Enter`: Desactiva el tutorial en pantalla e inicia el bucle principal de juego.  

- **HUD y Feedback en Tiempo Real**: La pantalla de juego actualiza la puntuación de forma dinámica y muestra *feedback* visual interactivo (como el texto de bonificación al lograr una alineación perfecta).  

- **Gestión Multimedia**: El usuario puede alternar (*toggle*) el estado de la música de fondo en cualquier momento utilizando la tecla `M`.  

- **Gestión de Estados Finales**: Al colisionar o caer, el sistema renderiza una pantalla de *Game Over* que recupera y muestra la puntuación máxima histórica, permitiendo reiniciar el estado del juego con `R` o finalizar la ejecución con `Esc`.  

---

## 📂 Arquitectura del Proyecto

El código está modularizado para garantizar su escalabilidad y fácil mantenimiento: 

- `main.py`: Punto de entrada de la aplicación y bucle principal (renderizado a 60 FPS)

- `Jugador.py` / `Plataforma.py` / `Puente.py`: Clases principales que encapsulan las propiedades y comportamientos de las entidades del juego.

- `pantalla_game_over.py`: Gestión de la interfaz de usuario al finalizar la partida.

- `Utils.py`: Funciones auxiliares para el manejo de I/O de archivos.

- `constantes.py`: Centralización de variables de entorno, rutas relativas y configuraciones globales para evitar *magic numbers*.

---

## 🚀 Instalación y Ejecución

El proyecto requiere Python 3.x y la librería `pygame` para su correcta ejecución.

1. Clona este repositorio en tu máquina local:
   ```bash
   git clone https://github.com/paulaschez/dinodash
    ```

2. Navega al directorio raíz del proyecto:
    ```bash
    cd dinodash
    ```

3. Instala las dependencias necesarias:
    ```bash
    pip install pygame
    ```

4. Ejecuta el archivo principal para compilar e iniciar el juego: 
    ```bash
    python main.py
    ```

---
**Autora:** Paula Sánchez Vélez · [@paulaschez](https://github.com/paulaschez)