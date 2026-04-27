Evaluación de rendimiento y análisis de parámetros de SWOOSH

Este repositorio contiene el análisis de rendimiento y la evaluación de parámetros del esquema de intercambio de claves no interactivo (NIKE) basado en retículos SWOOSH, construido sobre el problema Module Learning With Errors (M-LWE).

Resumen (Abstract)

Este trabajo analiza cómo la elección de parámetros influye en la seguridad, el coste computacional y la viabilidad práctica del esquema SWOOSH.

A partir de la implementación de referencia, se comparan resultados experimentales con los valores teóricos descritos por los autores originales, estudiando el equilibrio entre seguridad post-cuántica (superior a 120 bits) y eficiencia en el consumo de recursos.

Metodología

Para la obtención de métricas, se utilizó la implementación de referencia de SWOOSH desarrollada en Rust.

Entorno de ejecución: Linux sobre WSL2 (Windows Subsystem for Linux)
Herramientas: Benchmarking integrado en cargo
Comandos utilizados:
cargo build --release
cargo run --release --bin bench_scheme

Se realizaron múltiples ejecuciones con el objetivo de reducir la variabilidad y obtener resultados consistentes.

Resultados clave

A continuación se muestran los resultados obtenidos en las dos operaciones críticas del esquema, comparados con los valores de referencia de los autores (Gajland et al.):

Operación	Media (Ciclos)	Variación	Ref. (Ciclos)	Observación
KeyGen	~66–67M	2–3 %	—	Fase de alto coste computacional
skey_deriv	~4.4M	< 1 %	<12M	Alta eficiencia y estabilidad

Conclusiones del análisis
Consistencia: Los resultados experimentales confirman que la derivación de clave (skey_deriv) es altamente eficiente, incluso mejorando las referencias en determinados entornos.
Coste de la no interactividad: El esquema sacrifica tamaño de clave (~220 KB) y coste en KeyGen a cambio de eliminar la interacción entre las partes.
Viabilidad: SWOOSH se posiciona como una alternativa sólida en escenarios donde reducir la interacción es más importante que optimizar el ancho de banda.
