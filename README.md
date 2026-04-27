# Evaluación de rendimiento y análisis de parámetros de SWOOSH

Este repositorio contiene el análisis de rendimiento y la evaluación de parámetros del esquema de intercambio de claves no interactivo (**NIKE**) basado en retículos **SWOOSH**, construido sobre el problema **Module Learning With Errors (M-LWE)**.

---

## Resumen (Abstract)

Este trabajo analiza cómo la elección de parámetros influye en la seguridad, el coste computacional y la viabilidad práctica del esquema SWOOSH.

A partir de la implementación de referencia, se comparan resultados experimentales con los valores teóricos descritos por los autores originales, estudiando el equilibrio entre seguridad post-cuántica (superior a 120 bits) y eficiencia en el consumo de recursos.

---

## Metodología

Para la obtención de métricas, se utilizó la implementación de referencia de SWOOSH desarrollada en Rust.

- **Entorno de ejecución:** Linux sobre WSL2 (Windows Subsystem for Linux)  
- **Herramientas:** Benchmarking integrado en `cargo`  
- **Comandos utilizados:**

```bash
cargo build --release
cargo run --release --bin bench_scheme
