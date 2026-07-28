# Ficha de análisis
## 1. Nombre del Space
Nombre: TRELLIS.2

Enlace: https://huggingface.co/spaces/microsoft/TRELLIS.2

## 2. ¿Qué hace el agente?
Recibe de entrada una imagen y permite ajustar su resolucion y texturas para luego generar un modelo 3D de la imagen y poder descargarlo como un archivo GLB

## 3. Análisis PEAS
### Performance ¿Qué significa que el agente haga bien su trabajo? 
Que el modelo 3D generado sea geométricamente fiel y visualmente coherente con la imagen de entrada, desde cualquier ángulo de visualización.
### Environment ¿Con qué interactúa el agente? 
La imagen 2D subida por el usuario, la interfaz web de Hugging Face donde se configuran parámetros, y la infraestructura GPU en la nube que ejecuta el modelo.
### Actuators ¿Qué acciones produce? 
Genera y renderiza el modelo 3D y produce el archivo exportable para descarga.
### Sensors ¿Qué información recibe como entrada?
La imagen subida por el usuario junto con los parámetros de configuración seleccionados en la interfaz.

## 4. Clasificación del entorno

Propiedad Clasificación Justificación

### Observable: Parcial
El agente solo percibe la imagen 2D subida, no puede ver el objeto completo.
### Determinista: No
La misma imagen puede producir resultados ligeramente distintos en cada ejecución.
### Episódico: Sí  	
Cada generación 3D es independiente, el resultado de una imagen no depende de interacciones o generaciones anteriores.
### Estático: Sí  	
La imagen de entrada no cambia mientras el agente la procesa; el entorno permanece fijo durante la generación.
### Discreto: No  
Tanto la imagen de entrada como el objeto de salida son de naturaleza continua.
### Conocido: Sí  
El modelo de generación es conocido por sus diseñadores.


## 5. ¿Qué tipo de programa de agente creen que es?

### Agente basado en objetivos
TRELLIS.2 no actúa por simples reglas de condición-acción, sino que persigue un objetivo claro y explícito: generar un modelo 3D que represente fielmente el objeto de la imagen de entrada. Para lograrlo, internamente debe construir una representación de la estructura tridimensional a partir de la información 2D disponible, y orientar su proceso generativo hacia ese objetivo específico, en lugar de solo reaccionar a estímulos. No encaja como agente de utilidad puro porque no está balanceando múltiples objetivos en conflicto con una función de utilidad explícita, sino persiguiendo un objetivo concreto: la fidelidad del resultado 3D respecto a la imagen dada.
