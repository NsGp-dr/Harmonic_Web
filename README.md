# 🕸️ Harmonic Web

> Visualizadores de audio interactivos construidos sobre síntesis armónica, figuras de Lissajous y métricas de persistencia topológica. Todo corre en el navegador — sin dependencias, sin instalación.

---

## ¿Qué es esto?

**Harmonic Web** es una colección de experimentos de visualización audioreactiva donde señales oscilatorias se transforman en geometría viva. Cada archivo explora una forma distinta de correlacionar frecuencia, amplitud y fase con estructuras visuales que se autorecurren en el tiempo.

La lógica central: las bandas espectrales (bajos, medios, agudos) modulan parámetros geométricos independientes. La superposición de esas modulaciones produce patrones que nunca se repiten exactamente — pero siempre reconocen su estado anterior.

---

## Archivos

| Archivo | Descripción |
|---|---|
| [`index.html`](./index.html) | Punto de entrada principal — Harmonic Grid audioreactivo con modos Mesh, Radial y Flow |
| [`Harmonic_Geometry.html`](./Harmonic_Geometry.html) | Figuras de Lissajous con detección de pitch y acordes vía Web Audio API |
| [`Harmonic_Geometry_Morphing_Synth_Edition.html`](./Harmonic_Geometry_Morphing_Synth_Edition.html) | Geometría harmónica con síntesis de audio integrada — la visualización genera sonido y viceversa |
| [`Harmonic_Geometry_Persistent_Cycles_Edition.html`](./Harmonic_Geometry_Persistent_Cycles_Edition.html) | Versión con métricas de persistencia topológica para identificar ciclos estables en los patrones |
| [`Harmonic_Grid.html`](./Harmonic_Grid.html) | Malla deformada por audio — cada nodo responde a low/mid/high con distorsión espacial independiente |
| [`Water_glass.html`](./Water_glass.html) | Simulación de ondas en superficie líquida reactiva a frecuencias |

---

## Cómo usar

1. Clona o descarga el repositorio
2. Abre cualquier `.html` directamente en el navegador (Chrome / Firefox recomendado)
3. Permite acceso al micrófono cuando se solicite
4. Si no tienes audio disponible, activa el **modo demo** — señales LFO simulan entrada de audio

```bash
git clone https://github.com/NsGp-dr/Harmonic_Web.git
cd Harmonic_Web
# abre index.html en tu navegador
```

> No requiere servidor local, npm, ni ninguna dependencia externa.

---

## Tecnologías

- **Web Audio API** — captura de micrófono, análisis FFT, síntesis
- **Canvas 2D API** — renderizado de geometría y trazas
- **Vanilla JS** — sin frameworks, sin build tools
- **HTML5** — un solo archivo por experimento, autocontenido

---

## Conceptos matemáticos

**Figuras de Lissajous** — curvas paramétricas `x(t) = A·sin(aτ + δ)`, `y(t) = B·sin(bτ)` donde la razón `a/b` determina la topología de la figura. Las frecuencias de audio modulan `a`, `b` y `δ` en tiempo real.

**Autorecurrencia armónica** — la fase de cada punto de la malla acumula contribuciones de múltiples frecuencias espaciales. El término de recurrencia `sin(φ · 6π + amp · 4)` hace que la deformación reconozca su propio estado de fase anterior.

**Persistencia topológica** — en la edición `Persistent_Cycles`, los ciclos de la señal se rastrean usando métricas de homología persistente: los patrones que "sobreviven" más tiempo en el diagrama de persistencia son los armónicos más estables de la señal de entrada.

---

## Estructura de bandas espectrales

```
FFT bins → [ LOW 0–4% ] [ MID 4–25% ] [ HIGH 25–70% ] [ AIR 70–100% ]
               ↓              ↓               ↓
          deformación    frecuencia      detalle fino
          de baja freq   espacial media  y ruido
```

Cada banda conduce una capa de deformación espacialmente independiente. La suma produce el campo de desplazamiento total de la malla.

---

## Roadmap

- [ ] Modo exportar — captura de frames como PNG/GIF
- [ ] Control MIDI externo para parámetros de síntesis
- [ ] Versión TouchDesigner con OSC bridge
- [ ] Diagrama de persistencia visualizado en overlay

---

## Autor

**Nicolás Giraldo** · [@NsGp-dr](https://github.com/NsGp-dr)
[mail](nicolasantiagog@gmail.com)
Bogotá, Colombia

Investigación en visualización de datos, sonificación y análisis topológico aplicado a señales.
