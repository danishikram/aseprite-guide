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

⚠️ Nota: La ruta hace referencia a Visual Studio 2022. Ajusta si usas otra versión.  

---

## 📦 Preparar Skia  

Extrae Skia en la ruta:  

```bat
C:\deps\skia
```

---

## 🖥️ Compilar Aseprite  

Descarga el código fuente de Aseprite (v1.3.4) y colócalo en:  

```bat
C:\Aseprite
```

Crea la carpeta `build` dentro de Aseprite:  

```bat
mkdir C:\Aseprite\build
cd C:\Aseprite\build
```

Configura con CMake:  

```bat
cmake -DCMAKE_BUILD_TYPE=RelWithDebInfo ^
 -DLAF_BACKEND=skia ^
 -DSKIA_DIR=C:\deps\skia ^
 -DSKIA_LIBRARY_DIR=C:\deps\skia\out\Release-x64 ^
 -DSKIA_LIBRARY=C:\deps\skia\out\Release-x64\skia.lib ^
 -G Ninja ..
```

Compila con Ninja:  

```bat
ninja aseprite
```

---

## 📂 Resultado final  

El ejecutable estará en:  

```bat
C:\Aseprite\build\bin\aseprite.exe
```

¡Listo! 🎉 Ya tienes Aseprite v1.3.4 compilado.  

---

# 🇬🇧 English  

## 📋 Requirements  
- **System:** Windows 10 or 11  
- **Visual Studio:** 2022 Community with C++ tools  
- **CMake:** v3.28.3 (⚠️ exact version required)  
- **Ninja:** v1.11.1  
- **Skia:** m102  
- **Git**  

---

## 📂 Required Downloads  
- **Aseprite v1.3.4 Source Code**  
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

## ⚙️ Enable Visual Studio Environment  

```bat
call "C:\Program Files\Microsoft Visual Studio\2022\Community\Common7\Tools\VsDevCmd.bat" -arch=x64
```

⚠️ Note: This path refers to Visual Studio 2022. Adjust if using another version.  

---

## 📦 Prepare Skia  

Extract Skia into the following path:  

```bat
C:\deps\skia
```

---

## 🖥️ Build Aseprite  

Download Aseprite v1.3.4 source code and place it in:  

```bat
C:\Aseprite
```

Create the `build` folder inside Aseprite:  

```bat
mkdir C:\Aseprite\build
cd C:\Aseprite\build
```

Configure with CMake:  

```bat
cmake -DCMAKE_BUILD_TYPE=RelWithDebInfo ^
 -DLAF_BACKEND=skia ^
 -DSKIA_DIR=C:\deps\skia ^
 -DSKIA_LIBRARY_DIR=C:\deps\skia\out\Release-x64 ^
 -DSKIA_LIBRARY=C:\deps\skia\out\Release-x64\skia.lib ^
 -G Ninja ..
```

Build with Ninja:  

```bat
ninja aseprite
```

---

## 📂 Final Result  

The executable will be located at:  

```bat
C:\Aseprite\build\bin\aseprite.exe
```

Done! 🎉 You now have your compiled version of Aseprite v1.3.4.  
