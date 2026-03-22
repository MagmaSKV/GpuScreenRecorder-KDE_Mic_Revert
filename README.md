# GPU Screen Recorder - Mic Indicator Restored

Este repositorio compila automáticamente [gpu-screen-recorder](https://git.dec05eba.com/gpu-screen-recorder) con el ícono del micrófono restaurado en KDE Plasma.

## 🔧 ¿Qué hace?

Revertir el commit [`ff030ba`](https://github.com/dec05eba/gpu-screen-recorder/commit/ff030ba63f8d109618cbb69d759a5ce4c3cd802f) que eliminó la funcionalidad que mostraba el ícono del micrófono en el área de notificaciones de KDE cuando estaba en uso.

## 📦 Instalación

### Opción 1: Desde GitHub Releases

```bash
# Descargar la última versión
wget $(curl -s https://api.github.com/repos/TU_USUARIO/gpu-screen-recorder-mic/releases/latest | grep "browser_download_url" | cut -d '"' -f 4)

# Instalar
sudo pacman -U gpu-screen-recorder-mic-*.pkg.tar.zst