<div align="center">

# ⚡ FPGAeduDesign - Placas de Desarrollo

### *Empoderando a Creadores Digitales con Hardware Abierto*

**[🇬🇧 English](README.md)** | **[🇪🇸 Español](README.es.md)**

[![Licencia: MIT](https://img.shields.io/badge/Licencia-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![HDL](https://img.shields.io/badge/HDL-VHDL%20%7C%20Verilog-orange.svg)](/)
[![Plataforma](https://img.shields.io/badge/Plataforma-FPGA-success.svg)](/)
[![Documentación](https://img.shields.io/badge/Docs-Disponible-brightgreen.svg)](/)

---

### 🎯 Acerca de Este Repositorio

*Placas de desarrollo FPGA de grado profesional diseñadas para educación, prototipado y experimentación*

</div>

---

### 🔌 Línea de Placas de Desarrollo

<table>
<tr>
<td width="33%" align="center">

#### 🟢 **Explorer Lite-1k**

*Potencia de Nivel Inicial*

Perfecta para principiantes y entornos educativos

**Ideal para:**
- 📚 Aprender fundamentos
- 🎓 Proyectos educativos
- 🧪 Prototipado rápido

**[📖 Documentación](Explorer-Lite-1k/docs/)** | **[💻 Ejemplos](Explorer-Lite-1k/examples/)** | **[📦 Prebuilt](Explorer-Lite-1k/prebuilt/)**

</td>
<td width="33%" align="center">

#### 🟡 **Explorer Neo-5k**

*Campeón de Gama Media*

Rendimiento equilibrado para diseños intermedios

**Ideal para:**
- 🔧 Diseños lógicos complejos
- 🎮 Sistemas digitales
- 📡 Desarrollo de interfaces

**[📖 Documentación](Explorer-Neo-5k/docs/)** | **[💻 Ejemplos](Explorer-Neo-5k/examples/)** | **[📦 Prebuilt](Explorer-Neo-5k/prebuilt/)**

</td>
<td width="33%" align="center">

#### 🔴 **Explorer Edge-9k**

*Plataforma Avanzada*

Solución de alta capacidad para proyectos serios

**Ideal para:**
- 💻 Desarrollo de SoC
- 🚀 DSP avanzado
- 🎛️ Prototipado profesional

**[📖 Documentación](Explorer-Edge-9k/docs/)** | **[💻 Ejemplos](Explorer-Edge-9k/examples/)** | **[📦 Prebuilt](Explorer-Edge-9k/prebuilt/)**

</td>
</tr>
</table>

---

### 💡 Características Principales

<div align="center">

| Característica | Descripción |
|:--------------:|:------------|
| 🎨 **Soporte Dual HDL** | Ejemplos completos en VHDL y Verilog |
| 📦 **Binarios Pre-compilados** | Archivos .fs listos para flashear y probar al instante (sin compilación) |
| 🔍 **Prueba de Periféricos** | Proyectos de validación para todos los componentes integrados |
| 📖 **Enfoque Educativo** | Tutoriales paso a paso y código bien comentado |
| 🛠️ **Compatible con Gowin EDA** | Todos los proyectos incluyen archivos .gpr para fácil importación |
| ⚡ **Inicio Rápido** | Flashea binarios en segundos o compila desde código fuente |

</div>

---

### 📂 Estructura del Repositorio

```
FPGAeduDesign-Boards/
│
├── 🔷 Explorer-Lite-1k/
│   ├── 📄 docs/                    # Hojas de datos, guías de usuario, pines
│   ├── 🔧 hardware/                # Archivos PCB, esquemáticos, BOM
│   │
│   ├── 💻 examples/                # Ejemplos con código fuente completo
│   │   ├── vhdl/
│   │   │   ├── led_blink/
│   │   │   │   ├── src/            # Archivos fuente VHDL
│   │   │   │   ├── *.gpr           # Archivo de proyecto Gowin
│   │   │   │   └── README.md
│   │   │   ├── uart_test/
│   │   │   ├── spi_interface/
│   │   │   └── i2c_scanner/
│   │   │
│   │   └── verilog/
│   │       ├── led_blink/
│   │       │   ├── src/            # Archivos fuente Verilog
│   │       │   ├── *.gpr           # Archivo de proyecto Gowin
│   │       │   └── README.md
│   │       ├── uart_test/
│   │       └── spi_interface/
│   │
│   └── 📦 prebuilt/                # Binarios listos para flashear
│       ├── led_blink.fs            # Bitstream flash (sin código fuente)
│       ├── uart_test.fs
│       ├── peripheral_demo.fs
│       └── README.md               # Instrucciones de flasheo
│
├── 🔶 Explorer-Neo-5k/
│   ├── 📄 docs/
│   ├── 🔧 hardware/
│   ├── 💻 examples/
│   │   ├── vhdl/
│   │   └── verilog/
│   └── 📦 prebuilt/
│
├── 🔺 Explorer-Edge-9k/
│   ├── 📄 docs/
│   ├── 🔧 hardware/
│   ├── 💻 examples/
│   │   ├── vhdl/
│   │   └── verilog/
│   └── 📦 prebuilt/
│
└── 📚 docs/                        # Documentación general
    ├── primeros_pasos.md
    ├── configuracion_gowin.md
    ├── como_flashear.md
    └── preguntas_frecuentes.md
```

---

### 🚀 Inicio Rápido

**Opción 1: Flashear Binarios Pre-compilados (No requiere herramientas)**

```bash
# Clonar el repositorio
git clone https://github.com/FPGAeduDesign/FPGAeduDesign-Boards.git

# Navegar a la carpeta prebuilt de tu placa
cd FPGAeduDesign-Boards/Explorer-Neo-5k/prebuilt

# Flashear el bitstream usando Gowin Programmer
# Ver docs/como_flashear.md para instrucciones detalladas
```

**Opción 2: Compilar desde Código Fuente**

```bash
# Navegar a un proyecto de ejemplo
cd FPGAeduDesign-Boards/Explorer-Neo-5k/examples/vhdl/led_blink

# Abrir el archivo de proyecto Gowin
# Hacer doble clic en el archivo .gpr o abrirlo con Gowin EDA

# Compilar y programar mediante el IDE Gowin EDA
```

---

### 🎓 Ruta de Aprendizaje

```mermaid
graph LR
    A[🌱 Principiante] -->|Explorer Lite-1k| B[📚 Básico]
    B --> C[🔧 Intermedio]
    C -->|Explorer Neo-5k| D[⚡ Avanzado]
    D -->|Explorer Edge-9k| E[🚀 Experto]
```

---

### 🤝 Contribuciones

¡Aceptamos contribuciones! Ya sea:

- 🐛 Reportes de errores
- 💡 Solicitudes de características
- 📝 Mejoras en la documentación
- 🔧 Nuevos proyectos de ejemplo

Consulta nuestras [Guías de Contribución](CONTRIBUTING.md) para comenzar.

---

### 📜 Licencia

Este proyecto está licenciado bajo la **Licencia MIT** - consulta el archivo [LICENSE](LICENSE) para más detalles.

*¡Siéntete libre de aprender, modificar y construir sobre estos diseños!*

---

### 📞 Soporte y Comunidad

- 🌐 **Sitio Web**: [fpgaedudesign.com](https://fpgaedudesign.com)
- 💬 **Discord**: [Únete a nuestra comunidad](https://discord.gg/fpgaedudesign)
- 🐦 **Twitter**: [@FPGAeduDesign](https://twitter.com/fpgaedudesign)
- 📺 **YouTube**: [@FPGAeduDesign](https://youtube.com/@FPGAeduDesign)
- 📘 **Facebook**: [FPGAeduDesign](https://facebook.com/fpgaedudesign)
- 📸 **Instagram**: [@FPGAeduDesign](https://instagram.com/fpgaedudesign)
- 🎥 **Kick**: [FPGAeduDesign](https://kick.com/fpgaedudesign)
- 🎵 **TikTok**: [@FPGAeduDesign](https://tiktok.com/@fpgaedudesign)
- 📧 **Email**: support@fpgaedudesign.com
- 📖 **Wiki**: [Centro de Documentación](https://wiki.fpgaedudesign.com)

---

### 👨‍💻 Sigue al Creador

- 📘 **Facebook**: [rsgb24](https://facebook.com/rsgb24)
- 🎵 **TikTok**: [@rsgb24](https://tiktok.com/@rsgb24)

---

<div align="center">

**Hecho con ⚡ por el Equipo FPGAeduDesign**

⭐ *¡Dale una estrella si te resulta útil!* ⭐

</div>
