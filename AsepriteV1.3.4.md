# 🎨 Compilación de Aseprite v1.3.4 en Windows / Building Aseprite v1.3.4 on Windows  

Este documento explica paso a paso cómo compilar **Aseprite v1.3.4** en Windows.  
This document explains step by step how to build **Aseprite v1.3.4** on Windows.  

---

## 📑 Índice / Index  

1. [Español](#-español)  
   - [Requisitos](#-requisitos)  
   - [Descargas necesarias](#-descargas-necesarias)  
   - [Activar entorno de Visual Studio](#️-activar-entorno-de-visual-studio)  
   - [Preparar Skia](#-preparar-skia)  
   - [Compilar Aseprite](#️-compilar-aseprite)  
   - [Resultado final](#-resultado-final)  

2. [English](#-english)  
   - [Requirements](#-requirements)  
   - [Required Downloads](#-required-downloads)  
   - [Enable Visual Studio Environment](#️-enable-visual-studio-environment)  
   - [Prepare Skia](#-prepare-skia)  
   - [Build Aseprite](#️-build-aseprite)  
   - [Final Result](#-final-result)  

---

# 🇪🇸 Español  

## 📋 Requisitos  
- **Sistema:** Windows 10 o 11  
- **Visual Studio:** 2022 Community con herramientas C++  
- **CMake:** v3.28.3 (⚠️ versión exacta requerida)  
- **Ninja:** v1.11.1  
- **Skia:** m102  
- **Git**  

---

## 📂 Descargas necesarias  
- **Aseprite v1.3.4 Código fuente**  
  👉 [Aseprite v1.3.4 Release](https://github.com/aseprite/aseprite/releases/tag/v1.3.4)  

- **Git**  
  👉 [Download Git](https://git-scm.com/download/win)  

- **Visual Studio 2022 Community**  
  👉 [Download Visual Studio](https://visualstudio.microsoft.com/downloads/)  

- **CMake v3.28.3**  
  👉 [Download CMake 3.28.3](https://github.com/Kitware/CMake/releases/tag/v3.28.3)  

- **Ninja Build v1.11.1**  
  👉 [Download Ninja](https://github.com/ninja-build/ninja/releases/tag/v1.11.1)  

- **Skia m102**  
  👉 [Download Skia m102](https://github.com/aseprite/skia/releases/tag/m102-861e4743af)  

---

## ⚙️ Activar entorno de Visual Studio  

```bat
call "C:\Program Files\Microsoft Visual Studio\2022\Community\Common7\Tools\VsDevCmd.bat" -arch=x64
```

📦 Preparar Skia / Prepare Skia

Descarga Skia m102 desde el enlace anterior.
Download Skia m102 from the link above.

Extrae la carpeta en la siguiente ruta:

```bat
C:\deps\skia
```

👉 Al terminar deberías tener:
👉 At the end you should have:

```bat
C:\deps\skia\out\Release-x64\skia.lib
```

🖥️ Compilar Aseprite v1.3.4 / Build Aseprite v1.3.4

Descarga el código fuente de Aseprite (v1.3.4) y colócalo en:
Download the Aseprite source code (v1.3.4) and place it in:

```bat
C:\Aseprite
```

Crea la carpeta build dentro de Aseprite:
Create the build folder inside Aseprite:

```bat
mkdir C:\Aseprite\build
cd C:\Aseprite\build
```

Configura el proyecto con CMake:
Configure the project with CMake:

```bat
cmake -DCMAKE_BUILD_TYPE=RelWithDebInfo ^
 -DLAF_BACKEND=skia ^
 -DSKIA_DIR=C:\deps\skia ^
 -DSKIA_LIBRARY_DIR=C:\deps\skia\out\Release-x64 ^
 -DSKIA_LIBRARY=C:\deps\skia\out\Release-x64\skia.lib ^
 -G Ninja ..
```

Compila con Ninja:
Build with Ninja:

```bat
ninja aseprite
```
Resultado final / Final Result

El ejecutable estará en:
The executable will be in:


```bat
C:\Aseprite\build\bin\aseprite.exe
```

¡Listo! Ya tienes tu versión de Aseprite v1.3.4 compilada 🎨
Done! You now have your compiled version of Aseprite v1.3.4 🎨


Guía adaptada y simplificada para v1.3.4
