# Trabajo-de-Fin-de-Grados

Aplicación práctica que forma parte de la asignatura Trabajo de Fin de Grado de la Universidad de Granada. El propósito de esta experimentación será la de analizar las capacidades de varios de los modelos del lenguaje estudiados en la memoria frente a varias tareas del *Natural Language Processing*. 

En particular, se llevarán a cabo dos experimentos: 

* **Experimento 1**: Se aplicará el modelo *GPT-2* para la tarea de generación de discursos que simulen ser narrados por la reina de Inglaterra. Para ello se extraerá un corpus de discursos atribuidos a este personaje, se aplicará la técnica de *fine-tuning* al modelo *GPT-2* con este corpus y se generan diferentes pruebas.
    
* **Experimento 2** Se aplicará el modelo *BERT* para la tarea de completar oraciones de forma coherente. En este caso, el idioma del modelo y de la tarea será el español, ofreciendo así variedad y permitiendo la comparativa entre la realización de tareas con diferentes idiomas.

Se puede ejecutar Colab directamente desde el botón, donde tiene que elegir el fichero correspondiente: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/AlbertoEstep/Trabajo-de-Fin-de-Grados/)


## Experimento 1

El primer experimento realizado consiste en generar un discurso de la reina de Inglaterra, Isabel II. Para su ejecución, por un lado se obtendrá el corpus formado por 301 discursos de la casa real británica. A continuación de realizará una manipulación de dichos datos para que se ajusten al modelo elegido. Además se aplicará la técnica de *fine-tuning* al modelo con dicho corpus. Por último, se generarán varios discursos y se analizarán las características comunes de los textos generados y las específicas de alguno en particular.

Primero se hace uso del script *WebScrapingDiscursosReina.ipynb* [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/AlbertoEstep/Trabajo-de-Fin-de-Grados/blob/master/Experimento1/WebScrapingDiscursosReina.ipynb) para la obtención de los discursos. En nuestro caso se han guardado en la carpeta *./drive/My Drive/discursos_reina/* de Drive. El usuario puede obtenerlos ejecutando dicho fichero en Google Colab y conectándolo con su cuenta de Drive. De todos modos se incluye el zip *CorpusDiscursosReina.zip* con los discursos descargados.

Posteriormente se hace uso del script *CreacionFicherosEntrenamientoValidacion.ipynb* [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/AlbertoEstep/Trabajo-de-Fin-de-Grados/blob/master/Experimento1/CreacionFicherosEntrenamientoValidacion.ipynb) para realizar una manipulación de los datos y que se ajusten al modelo elegido.

A continuación se ejecutará el script *FineTuning.ipynb* [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/AlbertoEstep/Trabajo-de-Fin-de-Grados/blob/master/Experimento1/FineTuning.ipynb) para obtener el modelo ajustado con los datos del corpus. Se pueden variar los parámetros de llamada al scropt interno (*run_language_modeling.py*) para que ajuste el modelo de diversas maneras. Para más infomación consulte la memoria y la ayuda de los script.

Por último se ejecutará el script *GeneradorDiscursosReina.ipynb* [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/AlbertoEstep/Trabajo-de-Fin-de-Grados/blob/master/Experimento1/GeneradorDiscursosReina.ipynb) para generar los discursos deseados. De manera análoga al anterior script, se puede modificar la llamada al script interno (*run_generation.py*) para que genera diferentes discursos según los parámetros introducidos. Para más infomación consulte la memoria y la ayuda de los script.

## Experimento 2 

Se aplicará el modelo *BERT* para la tarea de completar oraciones de forma coherente. En este caso, el idioma del modelo y de la tarea será el español.

Para su ejecución simplemente hay que usar el script *MaskBertCastellano.ipynb* [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/AlbertoEstep/Trabajo-de-Fin-de-Grados/blob/master/Experimento2/MaskBertCastellano.ipynb) que descarga el modelo usado y ejecuta varios ejemplos de forma automática. Puede generar más ejemplos simplemente llamando a las funciones *completar_hueco* e *imprimir_frases* con la frase deseada.

Para mayor información, consulte la memoria.
