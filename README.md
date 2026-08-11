# ⚡Cyber Breach

**Un Top-Down Shooter táctico y motor de juego construido desde CERO absoluto usando C++ nativo y Win32 API.**

![Windows](https://img.shields.io/badge/OS-Windows-blue?style=for-the-badge&logo=windows)
![C++](https://img.shields.io/badge/C++-Native_Win32-00599C?style=for-the-badge&logo=c%2B%2B)
![Python](https://img.shields.io/badge/Backend-Python_Flask-FFD43B?style=for-the-badge&logo=python)

[![Descargar Instalador](https://img.shields.io/badge/📥_Descargar_Juego_(Instalador_Oficial)-28a745?style=for-the-badge)](https://github.com/Alexjando/Cyber_Breach/releases/latest/download/Cyber_Breach_Setup.exe)

---

En lugar de usar un motor comercial como Unity o Godot que resuelve las matemáticas por debajo de la mesa, me propuse el reto de:
1. Programar mi propio motor de renderizado (GDI), colisiones dinámicas y enjambres de partículas en **C++ puro**.
2. Crear una infraestructura de servidor backend en **Python (Flask)** alojada en la nube.
3. Crear un cliente HTTP asíncrono en C++ que se comunique con el servidor en tiempo real y sin bloquear el juego principal.
4. Implementar un **actualizador automático silencioso** (OTA) que descarga parches directamente desde GitHub.

## 🎮 Controles
* **W, A, S, D** - Moverse.
* **Ratón** - Apuntar.
* **Clic Izquierdo** - Disparar (Armas con daño de área, penetración y explosiones programadas a mano).
* **SHIFT** - Dash / Corte letal de energía (Daño cuerpo a cuerpo).
* **O** - Menú de Configuración Visual.
* **T / W** - Tienda de Mejoras Permanentes y Armería.
