## Módulos Profundos (Deep Modules)

De acuerdo con John Ousterhout, un módulo profundo es aquel que ofrece una interfaz sencilla mientras oculta complejidad interna significativa.

Debido a que Smart Task Assistant se encuentra en una etapa inicial de desarrollo, aún no existen módulos con una profundidad arquitectónica elevada. Sin embargo, la implementación del backend mediante FastAPI constituye la base para la construcción de módulos profundos en futuras iteraciones.

Por ejemplo, el endpoint principal expone una interfaz extremadamente simple:

```python
@app.get("/")
def home():
    return {"message": "Backend funcionando"}

Para evitar esta fuga de información se mantuvo una separación estricta entre frontend y backend. La interfaz solo interactúa con servicios definidos mediante endpoints, sin depender directamente de detalles internos de implementación, estructuras de almacenamiento o futuras integraciones con inteligencia artificial.

Esta estrategia permitió aplicar el principio de ocultamiento de información y reducir el acoplamiento entre componentes, facilitando la evolución futura del sistema.
