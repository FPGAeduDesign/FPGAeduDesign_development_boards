<div align="center">

# 💻 Ejemplos de Diseño FPGA

**[🇬🇧 English](README.md)** | **[🇪🇸 Español](README.es.md)**

</div>

---

Esta carpeta contiene ejemplos completos de diseño FPGA con código fuente completo en **VHDL** y **Verilog**. Cada proyecto incluye todos los archivos necesarios para compilar, simular y programar tu placa.

## 📂 Estructura de Carpetas

```
examples/
├── vhdl/                      # Ejemplos en VHDL
│   ├── led_blink/
│   ├── uart_echo/
│   ├── button_led/
│   ├── seven_segment/
│   ├── spi_test/
│   ├── i2c_scanner/
│   └── peripheral_demo/
│
└── verilog/                   # Ejemplos en Verilog
    ├── led_blink/
    ├── uart_echo/
    ├── button_led/
    ├── seven_segment/
    ├── spi_test/
    ├── i2c_scanner/
    └── peripheral_demo/
```

## 🎯 Ejemplos Disponibles

### 🟢 Nivel Principiante

| Proyecto | Descripción | Habilidades Aprendidas |
|----------|-------------|------------------------|
| **led_blink** | Parpadeo de LEDs a 1Hz | Divisores de reloj, E/S básica |
| **button_led** | Mapeo de botones a LEDs | Manejo de entradas, antirrebote |
| **seven_segment** | Contador en 7 segmentos | Conversión BCD, multiplexación |

### 🟡 Nivel Intermedio

| Proyecto | Descripción | Habilidades Aprendidas |
|----------|-------------|------------------------|
| **uart_echo** | Eco por UART | Comunicación serial, máquinas de estado |
| **spi_test** | Comunicación con flash SPI | Protocolo SPI, control de tiempos |

### 🔴 Nivel Avanzado

| Proyecto | Descripción | Habilidades Aprendidas |
|----------|-------------|------------------------|
| **i2c_scanner** | Escaneo de bus I2C | Protocolo I2C, bus multi-master |
| **peripheral_demo** | Integración completa del sistema | Diseño de sistemas, gestión de recursos |

## 🚀 Cómo Usar

### 1. Elige tu HDL

Selecciona **VHDL** o **Verilog** según tu preferencia u objetivos de aprendizaje:

```bash
# Para VHDL
cd vhdl/led_blink

# Para Verilog
cd verilog/led_blink
```

### 2. Abrir en Gowin EDA

Cada carpeta de proyecto contiene un archivo de proyecto `.gpr`:

1. Inicia **Gowin EDA**
2. Haz clic en **File → Open** o presiona `Ctrl+O`
3. Navega a la carpeta del proyecto
4. Selecciona el archivo `.gpr`
5. El proyecto se abrirá con todas las fuentes configuradas

### 3. Compilar el Proyecto

**Usando la GUI:**
1. Haz clic en **Process → Synthesize** (o presiona `F11`)
2. Haz clic en **Process → Place & Route** (o presiona `F9`)
3. Haz clic en **Process → Generate Bitstream** (o presiona `F5`)

**Usando la Consola TCL:**
```tcl
run all
```

### 4. Programar tu Placa

1. Conecta tu placa vía USB
2. Haz clic en **Tools → Programmer** (o presiona `Ctrl+Alt+F`)
3. Haz clic en **Scan Device**
4. Selecciona tu FPGA de la lista
5. El bitstream ya debería estar cargado
6. Haz clic en **Program/Configure**

## 📋 Contenido del Proyecto

Cada proyecto de ejemplo incluye:

```
nombre_proyecto/
├── README.md              # Documentación específica del proyecto
├── nombre_proyecto.gpr    # Archivo de proyecto Gowin
├── src/
│   ├── top.vhd/.v        # Archivo de diseño top-level
│   ├── modulo1.vhd/.v    # Archivos de diseño adicionales
│   └── modulo2.vhd/.v
├── constraints/
│   └── board.cst         # Restricciones de pines y timing
├── sim/
│   └── testbench.vhd/.v  # Testbench de simulación (si está disponible)
└── docs/
    ├── schematic.png     # Diagrama de bloques
    └── timing.png        # Diagrama de tiempos (si aplica)
```

## 🎓 Ruta de Aprendizaje

### Para Principiantes

1. **Comienza con:** `led_blink`
   - Entiende las señales de reloj
   - Aprende E/S básica
   - Familiarízate con el flujo de Gowin EDA

2. **Luego prueba:** `button_led`
   - Añade manejo de entradas
   - Aprende sobre antirrebote
   - Entiende lógica combinacional vs secuencial

3. **Siguiente paso:** `seven_segment`
   - Trabaja con codificación BCD
   - Aprende técnicas de multiplexación
   - Crea patrones de salida más complejos

### Para Usuarios Intermedios

4. **Avanza a:** `uart_echo`
   - Implementa máquinas de estado
   - Maneja comunicación serial
   - Trabaja con protocolos

5. **Continúa con:** `spi_test`
   - Domina protocolos seriales síncronos
   - Interfaz con hardware real (memoria flash)
   - Maneja requisitos de timing

### Para Usuarios Avanzados

6. **Desafíate con:** `i2c_scanner`
   - Implementa protocolos bidireccionales
   - Maneja escenarios multi-master
   - Depura problemas complejos de timing

7. **Completa con:** `peripheral_demo`
   - Integra múltiples subsistemas
   - Gestiona recursos eficientemente
   - Crea sistemas FPGA completos

## 🔧 Guía de Personalización

### Cambiar Frecuencia de Reloj

La mayoría de los diseños usan un divisor de reloj. Para modificar la velocidad de parpadeo o timing:

**VHDL:**
```vhdl
-- Original: parpadeo 1Hz (50MHz / 50000000 = 1Hz)
constant DIVIDER : integer := 50000000;

-- Modificado: parpadeo 2Hz
constant DIVIDER : integer := 25000000;
```

**Verilog:**
```verilog
// Original: parpadeo 1Hz
parameter DIVIDER = 50000000;

// Modificado: parpadeo 2Hz
parameter DIVIDER = 25000000;
```

### Adaptar a Diferentes Placas

Si estás usando una placa diferente de esta serie:

1. **Actualiza restricciones de pines** en `constraints/board.cst`
2. **Verifica la frecuencia de reloj** coincide con el oscilador de tu placa
3. **Revisa niveles de voltaje E/S** en las restricciones
4. **Ajusta direcciones de periféricos** si usas hardware diferente

### Agregar tus Propias Características

1. Crea una nueva rama: `git checkout -b mi-caracteristica`
2. Modifica los archivos fuente
3. Prueba exhaustivamente
4. Documenta tus cambios
5. ¡Considera contribuir de vuelta! (Ver [CONTRIBUTING.md](../CONTRIBUTING.md))

## 📊 Simulación

Algunos proyectos incluyen testbenches para simulación:

### Usando Simulador Gowin EDA

1. Abre el proyecto en Gowin EDA
2. Haz clic en **Tools → Simulator**
3. Añade archivos testbench si no están incluidos
4. Haz clic en **Run Simulation**
5. Visualiza formas de onda en el visor integrado

### Usando ModelSim/QuestaSim

```bash
# Compilar VHDL
vcom -work work src/*.vhd
vcom -work work sim/testbench.vhd

# Ejecutar simulación
vsim -do "run -all" work.testbench

# Para Verilog
vlog -work work src/*.v
vlog -work work sim/testbench.v
vsim -do "run -all" work.testbench
```

### Usando GHDL (solo VHDL, código abierto)

```bash
# Analizar archivos
ghdl -a src/*.vhd
ghdl -a sim/testbench.vhd

# Elaborar
ghdl -e testbench

# Ejecutar
ghdl -r testbench --wave=output.ghw

# Visualizar con GTKWave
gtkwave output.ghw
```

## 💡 Consejos y Buenas Prácticas

### Organización del Código
- ✅ Mantén los módulos pequeños y enfocados
- ✅ Usa nombres de señal significativos
- ✅ Comenta lógica compleja
- ✅ Sigue convenciones de nomenclatura consistentes

### Timing
- ✅ Siempre sincroniza entradas externas
- ✅ Evita bucles combinacionales
- ✅ Cumple restricciones de timing
- ✅ Usa resets síncronos cuando sea posible

### Depuración
- ✅ Empieza simple, añade complejidad gradualmente
- ✅ Usa LEDs para indicación rápida de estado
- ✅ Implementa salida de depuración por UART
- ✅ Simula antes de sintetizar

### Uso de Recursos
- ✅ Revisa reportes de utilización de recursos
- ✅ Optimiza rutas críticas
- ✅ Usa RAM de bloques eficientemente
- ✅ Considera el consumo de energía

## 🐛 Problemas Comunes

### Errores de Síntesis

**Problema:** "Signal not declared" (Señal no declarada)
- **Solución:** Verifica ortografía y alcance de declaraciones de señal

**Problema:** "Multiple drivers" (Múltiples conductores)
- **Solución:** Asegúrate que las señales solo se conduzcan desde un proceso/bloque always

**Problema:** "Type mismatch" (Tipos no coinciden)
- **Solución:** Verifica que los tipos de datos coincidan en las asignaciones

### Problemas de Timing

**Problema:** El diseño no cumple timing
- **Solución:** Añade etapas de pipeline, reduce profundidad lógica o baja frecuencia de reloj

**Problema:** Advertencias de metaestabilidad
- **Solución:** Añade flip-flops sincronizadores para entradas asíncronas

### Problemas de Hardware

**Problema:** El diseño no funciona en hardware pero simula bien
- **Solución:** Revisa archivo de restricciones, verifica estándares E/S, añade lógica de reset

**Problema:** Comportamiento intermitente
- **Solución:** Busca señales no inicializadas, añade resets apropiados

## 📚 Recursos Adicionales

- 📖 [Guía de Usuario Gowin EDA](https://www.gowinsemi.com/en/support/database/)
- 📘 [Referencia VHDL](https://www.ics.uci.edu/~jmoorkan/vhdlref/)
- 📗 [Referencia Verilog](https://www.asic-world.com/verilog/index.html)
- 🎥 [Tutoriales en Video](https://youtube.com/@FPGAeduDesign)
- 💬 [Discord de la Comunidad](https://discord.gg/fpgaedudesign)

## 🤝 Contribuir

¿Encontraste un bug o quieres mejorar un ejemplo?

1. Haz fork del repositorio
2. Crea tu rama de características: `git checkout -b feature/ejemplo-increible`
3. Haz commit de tus cambios: `git commit -m 'Añadir ejemplo increíble'`
4. Push a la rama: `git push origin feature/ejemplo-increible`
5. Abre un Pull Request

Ver [CONTRIBUTING.md](../../CONTRIBUTING.md) para guías detalladas.

## 📞 ¿Necesitas Ayuda?

- 🐛 **¿Encontraste un bug?** Abre un [issue](https://github.com/FPGAeduDesign/FPGAeduDesign-Boards/issues)
- 💬 **¿Tienes preguntas?** Únete a nuestro [Discord](https://discord.gg/fpgaedudesign)
- 📧 **Email de soporte:** support@fpgaedudesign.com
- 📖 **Documentación:** Consulta la [Wiki](https://wiki.fpgaedudesign.com)

---

<div align="center">

**¡Feliz programación!** 🚀 **¡No olvides revisar la [carpeta prebuilt](../prebuilt/) para binarios listos para flashear!**

</div>
