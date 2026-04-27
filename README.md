# Evaluación de rendimiento y análisis de parámetros de SWOOSH

Este repositorio contiene el análisis de rendimiento y la evaluación de parámetros del esquema de intercambio de claves no interactivo (NIKE) basado en retículos SWOOSH, basado en el problema Module Learning With Errors (M-LWE).

## Resumen (Abstract)

Este trabajo estudia cómo la elección de parámetros influye en la seguridad, el coste computacional y la viabilidad práctica del esquema SWOOSH. A partir de la implementación de referencia, se comparan resultados experimentales con los valores teóricos descritos por los autores originales, analizando el equilibrio entre seguridad post-cuántica (superior a 120 bits) y eficiencia en el consumo de recursos.

## Metodología

Para la obtención de métricas, se utilizó la implementación de referencia de SWOOSH desarrollada en Rust.

    Entorno de ejecución: Linux operando bajo WSL2 (Windows Subsystem for Linux).
    Herramientas: Benchmarking integrado en la suite de cargo.
    Comandos utilizados:
    bash

    cargo build --release
    cargo run --release --bin bench_scheme

    Usa el código con precaución.

Se realizaron múltiples ejecuciones para mitigar la variabilidad y asegurar la consistencia de los datos.

## Resultados Clave

A continuación se detallan los resultados obtenidos en las dos operaciones críticas del esquema, comparándolos con las referencias de los autores (Gajland et al.):

| Operación    | Media (Ciclos)     | Variación | Ref. (Ciclos) | Observación                      |
|--------------|--------------------|-----------|---------------|----------------------------------|
| KeyGen       | ~66–67 × 10⁶       | 2–3 %     | —             | Fase de alto coste computacional |
| skey_deriv   | ~4.4 × 10⁶         | < 1 %     | — / ~12 × 10⁶ | Alta eficiencia y estabilidad    |

## Conclusiones del Análisis

    Consistencia: Los resultados experimentales confirman que la derivación de clave (skey_deriv) es altamente eficiente, incluso superando las expectativas de las referencias bajo ciertos entornos.
    Coste de No Interactividad: El esquema sacrifica tamaño de clave (~220 KB) y coste en KeyGen a cambio de eliminar la interacción entre partes.
    Viabilidad: SWOOSH se presenta como una opción sólida para escenarios donde la reducción de interacción es prioritaria sobre el ancho de banda.

## Código fuente

Implementación oficial utilizada para los experimentos:  
- https://github.com/MQuaresma/pswoosh
