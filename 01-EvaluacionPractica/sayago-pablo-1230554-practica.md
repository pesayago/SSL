# Evaluación Práctica

## Seguir las instrucciones del repositorio: https://github.com/ssl-cursos/maquinas. La idea de la actividad es compilar, ejecutar y revisar el código y contestar las siguientes preguntas.

1. ¿Qué tipo de autómata corresponde a lr-conocido?

**Seria un AFD que reconoce el lenguaje cuyas palabras de ese lenguaje representan los numeros enteros (tanto positivos como negativos)** 

2. Diagramar y definir formalmente el autómata.

![AFD](https://drive.google.com/file/d/10mRqmKeFYq-A6R9Mm81ItJ9rtjwTi3N_/view?usp=drive_link "AFD")
https://drive.google.com/file/d/10mRqmKeFYq-A6R9Mm81ItJ9rtjwTi3N_/view?usp=drive_link

3. Comparar el lenguaje reconocido con el lenguaje constanteEntera que acepta decimales, octales y hexadecimales. ¿Puede ser que uno contenga al otro? Cuál a cuál?
4. ¿Son lenguajes infinitos
5. ¿Qué tipo de autómata corresponde a lic-clasico?
6. ¿Cuál es la menor palabra que reconoce este autómata?
7. ¿Qué estructura de datos utiliza este autómata?
8. ¿Con qué etapas del proceso de compilación se relaciona cada uno de estos autómatas?
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

| Variable	      | Tipo de dato	 | Sección de la variable	| Seccion de los datos |
|-----------------|------------------|--------------------------|----------------------|
| palabra		  |	                 |                          |                      |
| longitud_maxima |			         |                          |                      |
| pila			  |                  |                          |                      |
| sentido		  |	                 |                          |                      |  
| ptr_sentido	  |		             |                          |                      |

Observaciones:

* Las secciones son static, stack (puede ser a su vez automatico) y heap.
* Una variable puede guardarse en una región pero los datos pueden estar en otra.