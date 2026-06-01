# Sección 2: Anatomía de la Complejidad (Deep Modules vs. Shallow Modules)

## Módulos Profundos (Deep Modules)

Según John Ousterhout, un módulo profundo es aquel que ofrece una interfaz simple mientras oculta una cantidad significativa de complejidad interna.

Dentro del proyecto Smart Task Assistant, el backend desarrollado con FastAPI puede considerarse un módulo profundo. La interfaz expuesta mediante endpoints resulta sencilla para el consumidor del servicio, mientras que la lógica interna puede crecer progresivamente incorporando validaciones, reglas de negocio, persistencia de datos e integración con servicios de inteligencia artificial.

La simplicidad de la interfaz permite que otros componentes interactúen con el sistema sin necesidad de conocer detalles internos de implementación.

## Módulos Superficiales (Shallow Modules)

Durante las revisiones arquitectónicas se identificó el riesgo de fragmentar excesivamente el proyecto en múltiples componentes pequeños con responsabilidades limitadas.

Las propuestas iniciales de modularización excesiva podían generar dependencias innecesarias entre archivos y aumentar la complejidad estructural del sistema. Este comportamiento corresponde a lo que Ousterhout denomina módulos superficiales, donde la complejidad de uso es similar a la complejidad que intentan ocultar.

Para mitigar este problema se optó por consolidar responsabilidades relacionadas y mantener una estructura modular clara, evitando la proliferación de componentes innecesarios.

## Fuga de Información (Information Leakage)

Uno de los riesgos identificados durante el diseño fue permitir que detalles internos del backend se propagaran hacia la interfaz de usuario.

Para evitar esta fuga de información se mantuvo una separación estricta entre frontend y backend. La interfaz solo interactúa con servicios definidos mediante endpoints, sin depender directamente de detalles internos de implementación, estructuras de almacenamiento o futuras integraciones con inteligencia artificial.

Esta estrategia permitió aplicar el principio de ocultamiento de información y reducir el acoplamiento entre componentes, facilitando la evolución futura del sistema.
