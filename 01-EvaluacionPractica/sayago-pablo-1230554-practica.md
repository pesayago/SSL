# Evaluación Práctica

## Seguir las instrucciones del repositorio: https://github.com/ssl-cursos/maquinas.  La idea de la actividad es compilar, ejecutar y revisar el código y contestar las siguientes preguntas. 

*TP subido a github en https://github.com/pesayago/SSL/blob/main/01-EvaluacionPractica/sayago-pablo-1230554-practica.md*

1. ¿Qué tipo de autómata corresponde a lr-conocido?

> Seria un AFD que reconoce el lenguaje cuyas palabras de ese lenguaje representan los numeros enteros (tanto positivos como negativos)

2. Diagramar y definir formalmente el autómata.

> https://drive.google.com/file/d/10mRqmKeFYq-A6R9Mm81ItJ9rtjwTi3N_/view?usp=drive_link

3. Comparar el lenguaje reconocido con el lenguaje constanteEntera que acepta decimales, octales y hexadecimales. ¿Puede ser que uno contenga al otro? Cuál a cuál?

> Si, el lenguaje reconocido del punto anterior esta incluido en el lenguaje constanteEntera es un sub-lenguaje del mismo**

4. ¿Son lenguajes infinitos?

> Si, son lenguajes infinitos dado que la cantidad de palabras pertenecientes a esos lenguajes no se puede determinar (tiende a infinito)

5. ¿Qué tipo de autómata corresponde a lic-clasico?

> Es un automata finito con pila (AFP) que reconoce palabras del lenguaje del tipo "cadenas que empiezan con 'a' y terminan con 'b' y tienen misma cantidad de a's y de b's (a>=N y b>=N, siendo N>=1)

6. ¿Cuál es la menor palabra que reconoce este autómata?

> La menor palabra reconocida por este lenguaje es: ab

7. ¿Qué estructura de datos utiliza este autómata?

> Este automata utiliza la estructura de datos pila (colección lineal de elementos que opera bajo el principio de último en entrar, primero en salir (LIFO) )

8. ¿Con qué etapas del proceso de compilación se relaciona cada uno de estos autómatas?

> El automata finito (AF convertidos en AFD completo para que pueda implementarse computacionalmente) se relacionan con la etapa de analisis lexico y el automata finito con pila (AFP) se relaciona con la etapa de analisis sintactico.

9. Teniendo en cuenta está sección del código:
```
int determinar_estado_para(int estado, char simbolo) {
    static int TT[4][3] = {
    /*            S  D  O */
    /* 0- */    { 1, 2, 3},
    /* 1  */    { 3, 2, 3},
    /* 2+ */    { 3, 2, 3},
    /* 3  */    { 3, 3, 3}
    };
    return TT[estado][determinar_columna(simbolo)];
}
```
Según el apunte de Identificadores: ¿Qué significa la palabra static? ¿En dónde se guarda?

> La palabra static significa estatica (tipo de dato estatico)  La variable static se almacenan en el segmento de datos estaticos del programa, que es una región de la memoria diferente a la pila y el heap.

10. Teniendo en cuenta está sección del código:

```
int es_palabra(const char *palabra) {
    size_t longitud_maxima = strlen(palabra);
    t_pila *pila = CrearPila(longitud_maxima);
    int sentido = 42;
    int *ptr_sentido = &sentido;
...
}
```
Completar la siguiente tabla:

| Variable	      | Tipo de dato	      | Sección de la variable	 | Seccion de los datos |
|-----------------|-----------------------|--------------------------|----------------------|
| palabra		  |	puntero a tipo de dato char |                          |               |
| longitud_maxima |			             |                          |                      |
| pila			  |                      |                          |                      |
| sentido		  |	                     |                          |                        
| ptr_sentido	  |		             |                          |                      |

Observaciones:

* Las secciones son static, stack (puede ser a su vez automatico) y heap.
* Una variable puede guardarse en una región pero los datos pueden estar en otra.