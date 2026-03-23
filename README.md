# GPU Screen Recorder - Mic Indicator Restored

Este repositorio compila automáticamente [gpu-screen-recorder](https://git.dec05eba.com/gpu-screen-recorder) con el ícono del micrófono restaurado en KDE Plasma.

## 🔧 ¿Qué hace?

Revertir el commit [`ff030ba`](https://github.com/dec05eba/gpu-screen-recorder/commit/ff030ba63f8d109618cbb69d759a5ce4c3cd802f) que eliminó la funcionalidad que mostraba el ícono del micrófono en el área de notificaciones de KDE cuando estaba en uso.

## 📦 Instalación

### Opción 1: GitHub Releases

```bash
# Descargar la última versión a /tmp
cd /tmp
curl -s https://api.github.com/repos/MagmaSKV/GpuScreenRecorder-KDE_Mic_Revert/releases/latest | \
  grep "browser_download_url" | \
  grep -v "debug" | \
  cut -d '"' -f 4 | \
  wget -qi -

# Instalar el paquete
sudo pacman -U gpu-screen-recorder-*.pkg.tar.zst
```

### Opción 2: Arch Repository (pacman)

1. Agrega la siguiente línea a /etc/pacman.conf:

```
[gpu-screen-recorder-mic]
SigLevel = Optional TrustAll
Server = https://raw.githubusercontent.com/MagmaSKV/GpuScreenRecorder-KDE_Mic_Revert/repo
```

⚠️ **QUE SEA EL PRIMERO DE TODOS LOS REPOSITORIOS QUE TENGAS O SI TIENE OTRO EL PAQUETE NORMAL CON MAS PRIORIDAD LO DESCARGARA DE AHI Y NO DE ESTE, POR EJEMPLO:**

```
# MagmaSKV - gpu-screen-recorder (with reverted kde microphone icon commit)  <--- Este tendra prioridad sobre el de CachyOS, que tambien lo tiene compilado pero sin el commit revertido
[gpu-screen-recorder-mic]
SigLevel = Optional TrustAll
Server = https://raw.githubusercontent.com/MagmaSKV/GpuScreenRecorder-KDE_Mic_Revert/repo

# cachyos repos
[cachyos-extra-v3]
Include = /etc/pacman.d/cachyos-v3-mirrorlist
```
2. Actualizar repositorios

```sudo pacman -Syy```

3. Instalar paquete

```sudo pacman -S gpu-screen-recorder```

Deberias de ver que la version es "x.x.x-310"

Si no puedes ver cual es usando:

```
❯ sudo pacman -Ss gpu-screen-recorder
gpu-screen-recorder-mic/gpu-screen-recorder 5.12.5-310 [instalado]
    A shadowplay-like screen recorder for Linux. The fastest screen recorder for Linux
gpu-screen-recorder-mic/gpu-screen-recorder-debug 5.12.5-310
    Detached debugging symbols for gpu-screen-recorder
cachyos-extra-v3/gpu-screen-recorder 5.12.5-1.1 [instalado: 5.12.5-310]
    A shadowplay-like screen recorder for Linux. The fastest screen recorder for Linux
cachyos-extra-v3/gpu-screen-recorder-notification 1.1.1-1.1 [instalado]
    Notification in the style of ShadowPlay
cachyos-extra-v3/gpu-screen-recorder-ui 1.10.8-1.1 [instalado]
    A fullscreen overlay UI for GPU Screen Recorder in the style of ShadowPlay
extra/gpu-screen-recorder 5.12.5-1 [instalado: 5.12.5-310]
    A shadowplay-like screen recorder for Linux. The fastest screen recorder for Linux
extra/gpu-screen-recorder-notification 1.1.1-1 [instalado: 1.1.1-1.1]
    Notification in the style of ShadowPlay
extra/gpu-screen-recorder-ui 1.10.8-1 [instalado: 1.10.8-1.1]
    A fullscreen overlay UI for GPU Screen Recorder in the style of ShadowPlay
```
