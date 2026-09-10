# Bitácora - Semana 2



## 1. Datos de la actividad

- **Estudiantes:** Andrés Parada, Maddox Valbuena, Julián Cárdenas
- **Equipo:** Si Team
- **Semana:** 2
- **Fecha del laboratorio:** 2026-09-10
- **Fecha del taller:** 2026-09-10
- **Tema principal:** Almacenamiento
- **Pregunta de la semana:**  Los datos ya llegan limpios. ¿Dónde viven ahora y qué podemos preguntarles?

## 2. Prediccion antes de ejecutar

Antes de abrir o ejecutar el programa, responde:

1. **Que creo que va a ocurrir?**
   El programa limitará su almacenamiento a las primeras 10 lecturas válidas y descartará el resto en silencio. Esto ocurre porque la clase RepositorioLecturas inicializa su arreglo interno (lecturas) con una CAPACIDAD_INICIAL de 10. Cuando la variable "cantidad" alcanza este límite, el método agregar() simplemente retorna false en lugar de crecer para almacenar los 211 datos del archivo lecturas_ampliadas.csv.
2. **Que parte del programa o del algoritmo puede fallar?**
  El bloque condicional dentro del método agregar() en la línea 35 en la clase RepositorioLecturas. Al evaluar if (cantidad == lecturas.length), frena la adición y la actualización de la variable cantidad, volviendo inútil el repositorio a partir de la décima lectura.

3. **Como comprobare mi prediccion?**
   Al momento de ejecutar el programa revisaría la impresión en consola de "Lecturas almacenadas". Si mi predicción es correcta, solo registraría los primeros 10, y todos los demás los ignoraría en lugar de almacenarlos, por lo que va a ocurrir una perdida de información intencional de todo el documento, sin indicar ningún tipo de error.

## 3. Evidencia del laboratorio

### Resultado observado

Al intentar ejecutar la clase IngestaSensores.java el programa no imprimió el reporte de lecturas ni interactuó con el repositorio como se esperaba en la predicción. En su lugar ocurrió un error de ejecución porque según la impresión de consola se lanzó una excepción en consola: java.io.FileNotFoundException: lecturas_ampliadas.csv (El sistema no puede encontrar el archivo especificado). El sistema no puede encontrar el archivo lectuas_ampliadas.csv donde están los registros que vamos a almacenar, este error ocurre en la línea 52 al instanciar FileReader(ARCHIVO).

### Diferencia entre la prediccion y el resultado

Mi predicción analizaba la estructura de almacenamiento de los datos en memoria desde el arreglo lecturas. Esperaba que los datos fueran silenciosamente descartados luego del 10mo registro, sin embargo el resultado fue un fallo en la instancia inicial del sistema de archivos, no pudiendo el sistema llegar al repositorio si quiera para imprimir los primeros 10 registros.

### Error o comportamiento inesperado

- **Que ocurrio?** Un crash total por archivo no encontrado (FileNotFoundException), impidiendo cualquier ingreso de datos al sistema.
- **Por que ocurrió?** La constante ARCHIVO en la clase IngestaSensores busca el documento lecturas_ampliadas.csv mediante una ruta relativa. El error salta porque el archivo no se encuentra ubicado en el directorio raíz del proyecto de IntelliJ, o bien el nombre tiene alguna diferencia del que buscamos.
- **Como lo corregimos o que falta corregir?** Debo mover el archivo lecturas_ampliadas.csv a la carpeta raíz del proyecto (al mismo nivel que la carpeta src), o ajustar la ruta en el código. Una vez que el archivo sea detectado, podré volver a ejecutar el programa para observar finalmente el problema del límite de 10 posiciones en el arreglo.
## 4. Explicacion en lenguaje llano

Explica el concepto principal como se lo explicarias a una persona de doce
anos. Usa entre tres y cinco lineas y evita palabras tecnicas que no expliques.

> [Escribe aqui tu explicacion.]

### Ejemplo o analogia

[Relaciona el concepto con una situacion cotidiana. Explica que representa
cada parte de la analogia y donde deja de ser exacta.]

## 5. El vacio que encontre

Al intentar explicar el tema, identifica el punto que aun no comprendes bien.

- **Mi duda concreta es:** [Pregunta especifica, no "no entiendo nada".]
- **Lo que ya puedo explicar es:** [Parte que si comprendes.]
- **Para resolver la duda consulte:** [Clase, lectura, experimento, companero u otra fuente.]
- **Ahora lo entiendo asi:** [Respuesta escrita con tus palabras.]

## 6. Trazado de la solucion

Escoge una ejecucion, recorrido o caso representativo y trazalo paso a paso.
Incluye los valores importantes despues de cada paso.

| Paso | Estado de los datos o estructura | Decision o resultado |
|---|---|---|
| 1 | [Estado inicial] | [Que ocurre] |
| 2 | [Siguiente estado] | [Que ocurre] |
| 3 | [Siguiente estado] | [Que ocurre] |
| 4 | [Estado final] | [Que ocurre] |

**Completa o agrega filas si es necesario.** Si trabajaste con una estructura,
dibuja su estado en cada paso o inserta aqui una imagen legible.

## 7. Decision de diseño

Relaciona lo aprendido con la Plataforma de Monitoreo Ambiental Urbano.

- **Problema que debiamos resolver:** [Situacion concreta del sistema.]
- **Estructura, algoritmo o estrategia elegida:** [Nombre y uso.]
- **Alternativa descartada:** [Otra opcion razonable.]
- **Por que elegimos la primera:** [Ventaja y costo de la decision.]
- **Que evidencia respalda la decision:** [Prueba, medicion o comportamiento observado.]

## 8. Aporte al proyecto

- **Archivo(s) o modulo(s) trabajado(s):** [Rutas dentro del repositorio.]
- **Cambio realizado:** [Describe la funcionalidad agregada o modificada.]
- **Como se conecta con la capa anterior:** [Explica la integracion.]
- **Que queda pendiente para la siguiente semana:** [Tarea concreta.]

## 9. Commits realizados

Registra los commits que muestran tu aporte individual.

| Commit | Mensaje | Que demuestra |
|---|---|---|
| `[hash corto]` | `[mensaje del commit]` | [Cambio realizado] |
| `[hash corto]` | `[mensaje del commit]` | [Cambio realizado] |

## 10. Reexplicacion final

Despues del taller, vuelve a responder la pregunta de la semana en cinco lineas
o menos. Esta respuesta debe ser mas precisa que la de la seccion 4 y debe
incluir la razon de tu decision tecnica.

> [Escribe aqui tu reexplicacion final.]

## 11. Reflexion individual

Responde con honestidad:

1. **Lo que ahora puedo hacer y antes no podia:**
   [Respuesta.]
2. **El error o supuesto que mas me enseno:**
   [Respuesta.]
3. **La pregunta que llevaria a la proxima clase:**
   [Respuesta.]
4. **Que parte del trabajo fue realmente mia:**
   [Respuesta concreta.]

## Lista de verificacion antes de entregar

- [ ] Escribi la prediccion antes de consultar el resultado.
- [ ] Inclui evidencia concreta del laboratorio.
- [ ] Explique un concepto sin depender de jerga.
- [ ] Registre un vacio, una duda o un error real.
- [ ] Trace al menos un caso paso a paso.
- [ ] Justifique una decision del proyecto y una alternativa descartada.
- [ ] Registre mis commits y mi aporte individual.
- [ ] Deje claro que queda pendiente.
- [ ] Renombre el archivo con el formato `sXX-nombre.md`.
