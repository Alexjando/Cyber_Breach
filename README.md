# ⚡Cyber Breach

**Un Top-Down Shooter táctico y motor de juego construido desde CERO absoluto usando C++ nativo y Win32 API.**

![Windows](https://img.shields.io/badge/OS-Windows-blue?style=for-the-badge&logo=windows)
![C++](https://img.shields.io/badge/C++-Native_Win32-00599C?style=for-the-badge&logo=c%2B%2B)
![Python](https://img.shields.io/badge/Backend-Python_Flask-FFD43B?style=for-the-badge&logo=python)
![GDI+](https://img.shields.io/badge/Rendering-GDI+-orange?style=for-the-badge)

[![Descargar Instalador](https://img.shields.io/badge/📥_Descargar_Juego_(Instalador_Oficial)-28a745?style=for-the-badge)](https://github.com/Alexjando/Cyber_Breach/releases/download/v1.08/Cyber_Breach_Setup_v1.08.exe)

---

En lugar de usar un motor comercial como Unity o Godot que resuelve las matemáticas por debajo de la mesa, me propuse el reto de:

1. **Programar mi propio motor de renderizado** (GDI+), colisiones dinámicas y enjambres de partículas en **C++ puro**.
2. **Crear una infraestructura de servidor backend** en **Python (Flask)** alojada en la nube.
3. **Crear un cliente HTTP asíncrono en C++** que se comunique con el servidor en tiempo real y sin bloquear el juego principal.

## 🎮 Controles

| Tecla / Ratón | Acción |
|---------------|--------|
| **W, A, S, D** | Mover al jugador |
| **Ratón** | Apuntar |
| **Clic Izquierdo** | Disparar (daño de área, penetración y explosiones programadas a mano) |
| **SHIFT** | Dash / Corte letal de energía (daño cuerpo a cuerpo) |
| **ESPACIO** | Pausar / reanudar partida |
| **M** | Abrir menú principal / volver al menú |
| **ESC** | Salir del juego / volver atrás en menús |
| **T** | Tienda de mejoras permanentes |
| **W** | Armería (desbloquear y equipar armas) |
| **O** | Configuración visual (volumen, idioma) |
| **Q** | Misiones diarias |
| **B** | Reclamar bonus de racha diaria |
| **1, 2, 3** | Elegir mejora cuando aparece el menú de mejoras |
| **R** | Reintentar (en pantalla Game Over) |
| **L** | Cerrar sesión / Iniciar sesión |
| **ENTER** | Confirmar / Iniciar sesión / continuar |
| **TAB** | Cambiar campo (usuario / contraseña) |
| **F1** | Registrar nueva cuenta |
| **F2** | Jugar como invitado (sin cuenta) |
| **F3** | ¿Olvidaste tu contraseña? |

## 🛠️ Características

### Motor de juego (C++ nativo)
- **Renderizado propio** con GDI+ (sin motores comerciales)
- **Sistema de partículas** para explosiones, muertes de enemigos y efectos visuales
- **Colisiones dinámicas** con paredes y enemigos
- **Campo de distancia (distance field)** para movimiento inteligente de enemigos
- **Sistema de oleadas** con enemigos que escalan en dificultad
- **Jefes (bosses)** cada 10 oleadas
- **Sistema de audio** con miniaudio (música de fondo, SFX, latido cuando hay poca vida)

### Sistema de progresión y cuenta
- **Autenticación de usuario** con registro e inicio de sesión (servidor Flask remoto)
- **Modo invitado** para jugar sin cuenta (progreso guardado solo localmente)
- **Guardado encriptado** localmente con Windows DPAPI (token de sesión y datos de usuario)
- **Sincronización en la nube** del progreso (puntuación, oleada, créditos, mejoras desbloqueadas)
- **Mejoras permanentes**: Vida, Daño, Velocidad, Daga (daño de dash), Misiles
- **Armas desbloqueables**: Pistola, SMG, Escopeta, Lanzamisiles

### Misiones y desafíos
- **Misiones diarias** que rotan cada 24 horas (eliminar enemigos, alcanzar oleada, puntuación total, kills con dash, derrotar jefes)
- **Sistema de racha (streak)** con bonus de créditos por días consecutivos
- **Tabla de récords** local y en la nube

### Backend (Python Flask)
- API REST para autenticación (`/login`, `/register`)
- Guardado y carga de progreso en la nube (`/save`, `/load`)
- Alojado en PythonAnywhere



## 🎯 Diseño desde cero

Este proyecto fue construido intencionalmente sin depender de motores comerciales para comprender profundamente:

- **Matemáticas de juegos**: vectores, distancias, colisiones círculo-pared, raycasting
- **Patrones de diseño**: state machine para menús, object pooling para partículas
- **Redes**: cliente HTTP asíncrono con `wininet.h`, comunicación JSON con backend Flask
- **Seguridad**: cifrado de tokens con Windows DPAPI, Base64 para almacenamiento local
- **Audio**: sintetizado y streaming con miniaudio, control de volumen independiente para música y SFX

---

> **Nota**: El modo invitado guarda el progreso únicamente en el dispositivo local. Si desinstalas el juego o cambias de equipo, perderás ese progreso. Crea una cuenta para sincronizar tu avance en la nube.
