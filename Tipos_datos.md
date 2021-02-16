
<!-- rnb-text-begin -->

---
title: "Tipos de datos en R"
output:
  html_document: 
    toc: yes
    keep_md: yes
  html_notebook:
    toc: yes
    toc_float: yes
---


<!-- rnb-text-end -->



<!-- rnb-text-begin -->


## Tipos de datos y funciones para trabajar con tipos de datos

En R se pueden trabajar, principalmente, los siguientes tipos de datos:

1. Numéricos: numeric, double o integer.
2. Caracteres: character
3. Lógicos: logic
4. Fechas y tiempos (date y POSIXct)
5. **Vectores: vector y factor**
6. **Matrices: matrix**
7. Listas: lists
8. **Conjuntos de datos: data.frame y tibble**

Algunas funciones útiles para trabajar con tipos de datos son:

- La función `class()` identifica el tipo de dato. 
- La función `is._____()` cumple la misma función. Por ejemplo `is.numeric(23)` dará como respuesta TRUE.
- ¿Qué resultado proporciona la función `is.integer(4.3)`?
La función `as._____()` permite crear datos de un tipo particular. Por ejemplo `x <- as.numeric("23")` creará un objeto numérico con el número 23.

Ahora creen un objeto tipo integer e imprímalo en la consola. Use la función `is.integer( )` para verificar el tipo de datos:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->



<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


Pruebe qué sucede al usar las funciones `class( )` y `is.numeric( )` en este objeto. ¿Qué clase de objeto muestran estas dos clases?


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuY2xhc3MoaSlcbmlzLm51bWVyaWMoaSlcbmBgYCJ9 -->

```r
class(i)
is.numeric(i)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


¿Cuál es la clase resultante si hago operaciones entre numeric e integer? 


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuaiA8LSAxMFxuY2xhc3MoaiAqIGkpXG5gYGAifQ== -->

```r
j <- 10
class(j * i)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

Cree un objeto llamado `mi_nombre` con su nombre y use las funciones `class( )` y `is.character( )` para verificar el tipo de datos.


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->



<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

¿Qué función de R le podría servir para saber el número de caracteres que tiene el objeto mi_nombre?


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->



<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


## Fechas y tiempos: 

- Cree un objeto que se llame `birthday` y que incluya la fecha de su nacimiento, así:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuYmlydGhkYXkgPC0gXCIxOTg1LTA0LTIzXCJcbmNsYXNzKGJpcnRoZGF5KVxuYmlydGhkYXkgPC0gYXMuRGF0ZShcIjE5ODUtMDQtMjNcIilcbmNsYXNzKGJpcnRoZGF5KVxuYGBgIn0= -->

```r
birthday <- "1985-04-23"
class(birthday)
birthday <- as.Date("1985-04-23")
class(birthday)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


- Use la función `as.numeric` para determinar cuántos días pasaron entre el 1 de enero de 1970 y `birthday`.


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuYXMubnVtZXJpYyhiaXJ0aGRheSlcbmFudGVyaW9yIDwtIGFzLkRhdGUoXCIxOTY5LTEtMVwiKVxuYXMubnVtZXJpYyhhbnRlcmlvcilcbmBgYCJ9 -->

```r
as.numeric(birthday)
anterior <- as.Date("1969-1-1")
as.numeric(anterior)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

- Use una combinación de las funciones anteriores para estimar cuántos días han pasado desde la fecha de su cumpleaños y el día de hoy.


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->



<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


Cree un objeto que incluya su fecha y hora de nacimiento, así:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuYmlydGhfdGltZSA8LSBhcy5QT1NJWGN0KFwiMTk4NS0wNC0yMyAxNDowMFwiKVxuYGBgIn0= -->

```r
birth_time <- as.POSIXct("1985-04-23 14:00")
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


Calcule el número de segundos que han transcurrido entre el día de su nacimiento y enero 1 de 1970.


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->



<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


### Manejo de fechas con el paquete lubridate

Hoja de referencia paquete lubridate para manejar fechas de una manera más flexible: https://evoldyn.gitlab.io/evomics-2018/ref-sheets/R_lubridate.pdf

Por ejemplo, con este paquete se pueden crear fechas que vengan en cualquier orden:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxubGlicmFyeShsdWJyaWRhdGUpXG5mZWNoYSA8LSBtZHkoXCIwNy0zMC0yMDIwXCIpXG5heWVyIDwtIGR5bShcIjEzLzIwMjAvMDhcIilcbmNsYXNzKGZlY2hhKVxuYGBgIn0= -->

```r
library(lubridate)
fecha <- mdy("07-30-2020")
ayer <- dym("13/2020/08")
class(fecha)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


## Vectores

- Los vectores son el tipo  más importante en R y por tanto el más utilizado.
- Es muy útil para el análisis de datos porque las bases de datos (i.e. data,frame) son entendidos por R como una colección de vectores.
- Un vector es una colección de elementos del mismo tipo (numérico o caracter). 
- Las operaciones con vectores aplican la operación automáticamente a todos los elementos. 

Por ejemplo, creen el siguiente vector:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxudyA8LSBjKDEsIDIsIDMsIDQsIDUsIDYsIDcsIDgsIDksIDEwKVxud1xudyA8LSAxOjEwXG53XG5gYGAifQ== -->

```r
w <- c(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
w
w <- 1:10
w
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


Y este vector:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxueiA8LSBjKFwiSnVhblwiLCBcIkRhbmllbGFcIiwgXCJQZWRyb1wiLCBcIk1hcsOtYVwiKVxuelxuY2xhc3MoeilcbmBgYCJ9 -->

```r
z <- c("Juan", "Daniela", "Pedro", "María")
z
class(z)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


¿Qué tipo de dato se crea si intentan crear este vector?


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuYSA8LSBjKFwiSnVhblwiLCAxLCBcIkRhbmllbGFcIiwgMilcbmBgYCJ9 -->

```r
a <- c("Juan", 1, "Daniela", 2)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


¿Qué pasa si lo intentan forzar a que sea numérico?

<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuYSA8LSBhcy5udW1lcmljKGMoXCJKdWFuXCIsIDEsIFwiRGFuaWVsYVwiLCAyKSlcbmFcbmNsYXNzKGEpXG5gYGAifQ== -->

```r
a <- as.numeric(c("Juan", 1, "Daniela", 2))
a
class(a)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


### Operaciones con vectores

Realicen las siguientes operaciones:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxud1xudyAqIDNcblxudyArIDJcblxudyAtIDNcblxudyAvIDRcblxudyBeIDJcblxuc3FydCh3KVxuYGBgIn0= -->

```r
w
w * 3

w + 2

w - 3

w / 4

w ^ 2

sqrt(w)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

¿Qué pasa con los elementos de vector al realizar estas operaciones?

Creen el siguiente vector y hagan las operaciones descritas a continuación:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuYiA8LSAtNTo0XG5iXG5gYGAifQ== -->

```r
b <- -5:4
b
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->



<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxubGVuZ3RoKHcpXG5sZW5ndGgoYilcbmBgYCJ9 -->

```r
length(w)
length(b)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->



<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxud1xuYlxudyArIGJcblxudyAqIGJcblxuYGBgIn0= -->

```r
w
b
w + b

w * b

```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


Use la función `length( )` para determinar el tamaño del vector resultante en cada una de las anteriores operaciones.


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxubGVuZ3RoKHcpXG5sZW5ndGgoYilcbmxlbmd0aCh3ICsgYilcbmxlbmd0aCh3ICogYilcbmBgYCJ9 -->

```r
length(w)
length(b)
length(w + b)
length(w * b)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


¿Qué pasa si los dos vectores no son del mismo tamaño? Por ejemplo, creen el siguiente vector y realicen alguna operación para ver qué sucede:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuYyA8LSBjKDI6NSwgOCwgMTApXG5jXG5sZW5ndGgoYylcbmBgYCJ9 -->

```r
c <- c(2:5, 8, 10)
c
length(c)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->



<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxud1xuY1xudyArIGNcblxudyAqIGNcbmBgYCJ9 -->

```r
w
c
w + c

w * c
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


¿Qué pasa en las anteriores operaciones con el séptimo elemento del vector w?¿Con qué elemento del vector c se está relacionando?

Use la función `length( )` para determinar el tamaño del vector resultante en cada una de las anteriores operaciones.


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxubGVuZ3RoKHcgKyBjKVxubGVuZ3RoKHcgKiBjKVxuYGBgIn0= -->

```r
length(w + c)
length(w * c)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


## Comparaciones de vectores 

¿Cuál es el resultado de ejecutar las siguientes comparaciones?


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxueCA8LSBjKDIsMyw0LDYpXG55IDwtIGMoMSwzLDQsNSlcblxueCA8PSA1XG54ID49IHlcbnggPiB5XG54IDwgeVxueCA9PSB5XG5gYGAifQ== -->

```r
x <- c(2,3,4,6)
y <- c(1,3,4,5)

x <= 5
x >= y
x > y
x < y
x == y
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

La comparación se ejecuta respecto de cada par de elementos en los dos vectores. Por ejemplo, la función selecciona el segundo elemento del vector x y lo compara con el segundo elemento del vector y, y decide el resultado.

Si se quiere ejecutar la comparación respecto de todos los elementos de los dos vectores, pueden usar la función `all`, y si la comparación la quieren ejecutar respecto de cualquier elemento de los dos vectores, pueden usar la función `any`.


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuYWxsKHggPiB5KVxuYWxsKHggPj0geSlcbmFueSh4IDwgeSlcbmFueSh4IDw9IHkpXG5gYGAifQ== -->

```r
all(x > y)
all(x >= y)
any(x < y)
any(x <= y)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


## Vectores con valores faltantes
- La función `is.na()` permite identificar si un vector tiene valores faltantes:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuIyBDcmVhciB2ZWN0b3JcblxuZmFsdGFudGVzIDwtIHJlcCh4ID0gYyhOQSwgMjMsIE5BLCA0LCA4NSksIHRpbWVzID0gMjApXG5mYWx0YW50ZXNcbmxlbmd0aChmYWx0YW50ZXMpXG4jIFVzYXIgaXMubmEoKVxuXG5pcy5uYShmYWx0YW50ZXMpXG5cbmBgYCJ9 -->

```r
# Crear vector

faltantes <- rep(x = c(NA, 23, NA, 4, 85), times = 20)
faltantes
length(faltantes)
# Usar is.na()

is.na(faltantes)

```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

- ¿Qué pasa si usa `as.numeric(is.na(faltantes))`? ¿Cuál es el resultado?


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuYXMubnVtZXJpYyhpcy5uYShmYWx0YW50ZXMpKVxuYGBgIn0= -->

```r
as.numeric(is.na(faltantes))
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


- ¿Cuántos valores faltantes tiene este vector?


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuc3VtKGFzLm51bWVyaWMoaXMubmEoZmFsdGFudGVzKSkpXG5zdW0oaXMubmEoZmFsdGFudGVzKSlcbmBgYCJ9 -->

```r
sum(as.numeric(is.na(faltantes)))
sum(is.na(faltantes))
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


## Explorar el contenido de los vectores

En el caso del vector x, si quiero ver solamente un elemento del vector uso [ ]:

<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuIyBMYSBmdW5jacOzbiBzYW1wbGUgIHBlcm1pdGUgdG9tYXIgbXVlc3RyYXMgYWxlYXRvcmlhcyBkZSB1biBjb25qdW50byBkZSBkYXRvczpcbnkgPC0gc2FtcGxlKHggPSAxOjEwMDAwLCBzaXplID0gMTAwMClcbmxlbmd0aCh5KVxueVxucHJpbnQoeSlcbiMgUG9yIGVqZW1wbG8sIHNpIHF1aWVybyB2ZXIgZWwgdGVyY2VyIGVsZW1lbnRvIGRlbFxuIyB2ZWN0b3IgOlxueVszXVxuIyBPIGVsIDUwOlxueVs1MF1cbiMgWSBwYXJhIHZlciBsb3MgZWxlbWVudG9zIDQ1IGFsIDU1OlxueVs0NTo1NV1cbnlbeSA8IDUwMF1cbnlbeSA8IDEwXVxuIyBJZ3VhbG1lbnRlLCBzaSBxdWllcm8gdmVyIGxvcyBlbGVtZW50b3MgZGVsXG4jIHZlY3RvciBmYWx0YW50ZXMgcXVlIHNlYW4gbmE6XG5mYWx0YW50ZXNbaXMubmEoZmFsdGFudGVzKV1cbiMgWSBsb3MgcXVlIG5vIHNvbiB2ZWN0b3JlcyBmYWx0YW50ZXM6XG5mYWx0YW50ZXNbIWlzLm5hKGZhbHRhbnRlcyldXG5jb21wbGV0b3MgPC0gZmFsdGFudGVzWyFpcy5uYShmYWx0YW50ZXMpXVxuY29tcGxldG9zXG5gYGAifQ== -->

```r
# La función sample  permite tomar muestras aleatorias de un conjunto de datos:
y <- sample(x = 1:10000, size = 1000)
length(y)
y
print(y)
# Por ejemplo, si quiero ver el tercer elemento del
# vector :
y[3]
# O el 50:
y[50]
# Y para ver los elementos 45 al 55:
y[45:55]
y[y < 500]
y[y < 10]
# Igualmente, si quiero ver los elementos del
# vector faltantes que sean na:
faltantes[is.na(faltantes)]
# Y los que no son vectores faltantes:
faltantes[!is.na(faltantes)]
completos <- faltantes[!is.na(faltantes)]
completos
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

**El signo `!` permite hacer negaciones en R**

Uso de la función sample para replicar el lanzamiento de dos dados de seis caras:

<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuc2FtcGxlKHggPSAxOjYsIHNpemUgPSAyLCByZXBsYWNlID0gVFJVRSlcbmBgYCJ9 -->

```r
sample(x = 1:6, size = 2, replace = TRUE)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


## Factores

Un factor es un vector o un conjunto de datos que tiene categorías que se repiten (i.e. info de una variable categórica). Para crear un factor, o transformar un vector normal a un factor se usa la función *as.factor( )*. Por ejemplo, creen el siguiente factor:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuY2FycmVyYSA8LSBmYWN0b3IoYyhcIkRlcmVjaG9cIiwgXCJFY29ub23DrWFcIiwgXG4gICAgXCJHb2JpZXJub1wiLCBcIlRyYWJham8gU29jaWFsXCIsIFwiRmluYW56YXNcIiwgXG4gICAgXCJEZXJlY2hvXCIsIFwiRGVyZWNob1wiLCBcIkVjb25vbcOtYVwiLCBcIkVjb25vbcOtYVwiLCBcbiAgICBcIkZpbmFuemFzXCIpKVxuY2xhc3MoY2FycmVyYSlcbmNhcnJlcmFcbmBgYCJ9 -->

```r
carrera <- factor(c("Derecho", "Economía", 
    "Gobierno", "Trabajo Social", "Finanzas", 
    "Derecho", "Derecho", "Economía", "Economía", 
    "Finanzas"))
class(carrera)
carrera
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


- Además del contenido del vector, en los factores se indican los niveles de los factores. 

- La función `table( )` nos permite ver un resumen de este vector. 


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxudGFibGUoY2FycmVyYSlcbmBgYCJ9 -->

```r
table(carrera)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


- La función `prop.table()`, aplicada sobre la función `table()` nos permite calcular las frecuencias relativas.


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxucHJvcC50YWJsZSh0YWJsZShjYXJyZXJhKSlcbnByb3AudGFibGUodGFibGUoY2FycmVyYSkpICogMTAwXG5gYGAifQ== -->

```r
prop.table(table(carrera))
prop.table(table(carrera)) * 100
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


- ¿Qué obtienen si ejecutan la función `as.numeric( )` sobre este factor?


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuY2FycmVyYVxuYXMubnVtZXJpYyhjYXJyZXJhKVxuYGBgIn0= -->

```r
carrera
as.numeric(carrera)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

## Factores Ordenados

En el caso anterior el orden de los niveles no es relevante. ¿Qué pasa cuando si es relevante? 


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxubml2ZWxfZWR1Y2F0aXZvIDwtIHNhbXBsZSh4ID0gYyhcInByaW1hcmlhXCIsIFwiYmFjaGlsbGVyYXRvXCIsIFwicHJlZ3JhZG9cIiwgXCJwb3NncmFkb1wiKSwgc2l6ZSA9IDEwMCwgcmVwbGFjZSA9IFRSVUUpXG5jbGFzcyhuaXZlbF9lZHVjYXRpdm8pXG5cbm5pdmVsX2VkdWNhdGl2byA8LSBmYWN0b3Iobml2ZWxfZWR1Y2F0aXZvLCBsZXZlbHMgPSBjKFwicHJpbWFyaWFcIiwgXG4gICAgXCJiYWNoaWxsZXJhdG9cIiwgXCJwcmVncmFkb1wiLCBcInBvc2dyYWRvXCIpLCBcbiAgICBvcmRlcmVkID0gVFJVRSlcbm5pdmVsX2VkdWNhdGl2b1xuY2xhc3Mobml2ZWxfZWR1Y2F0aXZvKVxuYGBgIn0= -->

```r
nivel_educativo <- sample(x = c("primaria", "bachillerato", "pregrado", "posgrado"), size = 100, replace = TRUE)
class(nivel_educativo)

nivel_educativo <- factor(nivel_educativo, levels = c("primaria", 
    "bachillerato", "pregrado", "posgrado"), 
    ordered = TRUE)
nivel_educativo
class(nivel_educativo)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

Usen `table()` y `prop.table()` para ver un resumen de este vector.


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxudGFibGUobml2ZWxfZWR1Y2F0aXZvKVxucHJvcC50YWJsZSh0YWJsZShuaXZlbF9lZHVjYXRpdm8pKVxuYGBgIn0= -->

```r
table(nivel_educativo)
prop.table(table(nivel_educativo))
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

## Matrices

Para crear una matriz se usa la función `matrix`. Por ejemplo, la siguiente función crea una matriz de 5 x 2:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuQSA8LSBtYXRyaXgoMToxMCwgbmNvbCA9IDIpXG5BXG5cblogPC0gbWF0cml4KDE6MTAsIG5yb3cgPSA1LCBieXJvdyA9IFRSVUUpXG5aXG5gYGAifQ== -->

```r
A <- matrix(1:10, ncol = 2)
A

Z <- matrix(1:10, nrow = 5, byrow = TRUE)
Z
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


El argumento `nrow = ` determina el número de filas de la matriz. Si no se usa el argumento, por defecto la matriz queda de una columna. 

Las funciones `nrow`, `ncol` y `dim` sirven para explorar las dimensiones de la matriz. 


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxubnJvdyhBKVxuYGBgIn0= -->

```r
nrow(A)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->



Para acceder a elementos de la matriz se usa la siguiente notación:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuQVsxLDFdICMgTm9zIG11ZXN0cmEgZWwgZWxlbWVudG8gaT0xLCBqPTEgZGUgbGEgbWF0cml6IEEuXG5BWzQsIDJdXG5BWzEsIF0gIyBOb3MgbXVlc3RyYSBsYSBwcmltZXJhIGZpbGEgZGUgbGEgbWF0cml6IEEuXG5BWzMsIF1cbkFbICwxXSAjIE5vcyBtdWVzdHJhIGxhIHByaW1lcmEgY29sdW1uYSBkZSBsYSBtYXRyaXogQS5cbkFbICwyXVxuYGBgIn0= -->

```r
A[1,1] # Nos muestra el elemento i=1, j=1 de la matriz A.
A[4, 2]
A[1, ] # Nos muestra la primera fila de la matriz A.
A[3, ]
A[ ,1] # Nos muestra la primera columna de la matriz A.
A[ ,2]
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


### Operaciones con matrices:

Creen la siguiente matriz:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuQiA8LSBtYXRyaXgoMjE6MzAsIG5yb3cgPSA1KVxuQlxuY2xhc3MoQilcbmBgYCJ9 -->

```r
B <- matrix(21:30, nrow = 5)
B
class(B)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


Suma de matrices:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuQSArIEJcbmBgYCJ9 -->

```r
A + B
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

Producto de matrices:

Este producto requiere que el número de columnas de la matriz de la izquierda sea igual al número de filas en la derecha. En este caso A y B son 5 x 2, entonces primero transponemos B con la función `t` para poder calcular el producto:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuQl9UIDwtIHQoQilcbkJfVFxuQSAlKiUgQl9UXG5gYGAifQ== -->

```r
B_T <- t(B)
B_T
A %*% B_T
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


Inversa de una matriz cuadrada:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuRCA8LSBtYXRyaXgoYyg1LCA3LCAyLCAzKSwgbnJvdyA9IDIpXG5EXG5FIDwtIHNvbHZlKEQpXG5FXG5EICUqJSBFXG5yb3VuZChEICUqJSBFKVxuYGBgIn0= -->

```r
D <- matrix(c(5, 7, 2, 3), nrow = 2)
D
E <- solve(D)
E
D %*% E
round(D %*% E)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

El producto de una matriz cuadrada y su inversa es la matriz identidad.

### Unir matrices (`cbind` y `rbind`)


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuQVxuXG5DIDwtIHJlcCgxLCA1KVxuXG5BX2dyYW5kZSA8LSBjYmluZChBLCBDKVxuQSA8LSBjYmluZChDLCBBKVxuQVxuXG5CXG5CIDwtIHJiaW5kKEIsIGMoMCwgMCkpXG5CXG5gYGAifQ== -->

```r
A

C <- rep(1, 5)

A_grande <- cbind(A, C)
A <- cbind(C, A)
A

B
B <- rbind(B, c(0, 0))
B
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->



<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuQSA8LSBtYXRyaXgoMToxMCwgbmNvbCA9IDIpXG5DIDwtIHJlcCgxLCA1KVxuQV9ncmFuZGUgPC0gY2JpbmQoQSwgQylcbkFfZ3JhbmRlXG5BX2dyYW5kZTIgPC0gY2JpbmQoQywgQVsgLCAyXSwgQVsgLDFdKVxuQV9ncmFuZGUyIDwtIGNiaW5kKEFbICwgMl0sIEMsIEFbICwxXSlcbkFfZ3JhbmRlMlxuY29sbmFtZXMoQV9ncmFuZGUyKVxuY29sbmFtZXMoQV9ncmFuZGUyKSA8LSBjKFwiQ1wiLCBcIkExXCIsIFwiQTJcIilcbkFfZ3JhbmRlMlxuXG5sbShBMSB+IEEyLCBkYXRhID0gQV9ncmFuZGUyKVxuYGBgIn0= -->

```r
A <- matrix(1:10, ncol = 2)
C <- rep(1, 5)
A_grande <- cbind(A, C)
A_grande
A_grande2 <- cbind(C, A[ , 2], A[ ,1])
A_grande2 <- cbind(A[ , 2], C, A[ ,1])
A_grande2
colnames(A_grande2)
colnames(A_grande2) <- c("C", "A1", "A2")
A_grande2

lm(A1 ~ A2, data = A_grande2)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->



## Conjuntos de datos: `data.frame` y `tibble`

### `data.frame`:

- Un data.frame es un conjunto de datos conformado por filas y columnas. 
- Las filas contienen observaciones y las columnas variables. 
- Cada columna del data.frame es, en últimas, un vector. 
- Cada columna solamente puede tener datos de un tipo. 
- Pero el data.frame puede tener datos de distinto tipo en diferentes columnas. 

### `tibble`: un tipo particular de data.frame

Diferencias con un data.frame:

- No cambia la clase de los datos, en particular no cambia *strings* a *factores*.
- No crea números de filas.
- Nunca cambia los nombres de las variables.
- Cuando se muestra en la consola, incluye información sobre el tipo de variable, y muestra solamente lo que se alcanza a ver en la pantalla.
- Permite usar nombres de variables que no son usualmente validos en R (**Aunque esto no es recomendado**):


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxubGlicmFyeSh0aWR5dmVyc2UpXG50YiA8LSB0aWJibGUoXG4gICAgICBgOilgID0gXCJzbWlsZVwiLFxuICAgICAgYCBgID0gXCJzcGFjZVwiLFxuICAgICAgYDIwMDBgID0gXCJudW1iZXJcIilcbnRiXG5gYGAifQ== -->

```r
library(tidyverse)
tb <- tibble(
      `:)` = "smile",
      ` ` = "space",
      `2000` = "number")
tb
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


Por ahora vamos a cargar una base de datos del paquete `gapminder`. Si no lo tienen instalado, instálenlo antes de ejecutar el siguiente código:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuIyBpbnN0YWxsLnBhY2thZ2VzKFwiZ2FwbWluZGVyXCIpXG5saWJyYXJ5KGdhcG1pbmRlcilcbmRhdGEoZ2FwbWluZGVyKVxuY2xhc3MoZ2FwbWluZGVyKVxuYGBgIn0= -->

```r
# install.packages("gapminder")
library(gapminder)
data(gapminder)
class(gapminder)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


gapminder es un tibble. ¿Cómo se comportaría si fuera un data.frame?


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuZ2FwbWluZGVyMiA8LSBhcy5kYXRhLmZyYW1lKGdhcG1pbmRlcilcbmdhcG1pbmRlcjJcbmBgYCJ9 -->

```r
gapminder2 <- as.data.frame(gapminder)
gapminder2
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


### Funciones básicas para data.frames:

¿Cómo puedo saber las dimensiones de este conjunto de datos?

- Las funciones `nrow()` y `ncol()` permiten saber el número de filas y columnas respectivamente. 

- La función `dim()` proporciona ambas. 

- La función `names()` proporciona los nombres de las variables.

- La función `head()` muestra, por defecto, las primeras 5 filas. 

- La función `tail()` muestra, por defecto, las últimas 5 filas.

- **Modifiquen la función head() para que muestre las primeras 15 filas**


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->



<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

### Acceder a las columnas de un data.frame:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjpbIiMgTGEgc2lndWllbnRlIGZ1bmNpw7NuIG5vIHByb2R1Y2UgZXJyb3IgcG9ycXVlIGNvbXBsZXRvcyBleGlzdGUgZW4gZWwgZXNwYWNpbyBkZSB0cmFiYWpvIiwieCA8LSBzZXEoZnJvbSA9IDEwLCB0byA9IDEwMCwgYnkgPSAwLjUpIiwibWVhbih4KSIsIiMgU2luIGVtYmFyZ28gbGEgc2lndWllbnRlIGZ1bmNpw7NuIGdlbmVyYXLDrWEgdW4gZXJyb3IgcG9ycXVlIGVzZSBvYmpldG8gbm8gZXhpc3RlLCBwdWVzIGVzIHVuYSB2YXJpYWJsZSBxdWUgZXN0w6EgREVOVFJPIGRlbCBkYXRhLmZyYW1lIiwibWVhbihsaWZlRXhwKSJdfQ== -->

```r
# La siguiente función no produce error porque completos existe en el espacio de trabajo
x <- seq(from = 10, to = 100, by = 0.5)
mean(x)
# Sin embargo la siguiente función generaría un error porque ese objeto no existe, pues es una variable que está DENTRO del data.frame
mean(lifeExp)
```



<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


3 maneras:

1. Usando el signo `$` :

<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiZ2FwbWluZGVyJGxpZmVFeHAifQ== -->

```r
gapminder$lifeExp
```



<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

¿Qué clase o tipo de datos es la variable `continent`?


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuY2xhc3MoZ2FwbWluZGVyJGNvbnRpbmVudClcbmNsYXNzKGdhcG1pbmRlciRnZHBQZXJjYXApXG5gYGAifQ== -->

```r
class(gapminder$continent)
class(gapminder$gdpPercap)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

¿Cuál es el promedio de la variable `lifeExp`?


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxubWVhbihnYXBtaW5kZXIkbGlmZUV4cClcbmBgYCJ9 -->

```r
mean(gapminder$lifeExp)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

2. Usando `[x,y]`: En este caso, el primer numero corresponde al número de la fila y el segundo al de la columna. Para ver una columna completa dejamos vacío el primer número y ponemos el número de la columna. 


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuZ2FwbWluZGVyWywyXVxuYGBgIn0= -->

```r
gapminder[,2]
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


Para ver una secuencia de columnas:

<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuYmFzZSA8LSBnYXBtaW5kZXJbICwyOjRdXG5cbmBgYCJ9 -->

```r
base <- gapminder[ ,2:4]

```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->

Para ver columnas que no están seguidas:

<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuZ2FwbWluZGVyWyAsIGMoMSw0KV1cbmBgYCJ9 -->

```r
gapminder[ , c(1,4)]
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


¿Cómo podrían mostrar las primeras 5 observaciones de las columnas 2 y 4? ¿Y las observaciones 2 y 4 de las mismas columnas?


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuZ2FwbWluZGVyWzE6NSwgYygyLCA0KV1cbmdhcG1pbmRlcltjKDIsNCksIGMoMiw0KV1cblxuZ2FwbWluZGVyW2dhcG1pbmRlciRjb3VudHJ5PT1cIkNvbG9tYmlhXCIsIF1cbmBgYCJ9 -->

```r
gapminder[1:5, c(2, 4)]
gapminder[c(2,4), c(2,4)]

gapminder[gapminder$country=="Colombia", ]
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


3. Por nombre de las columnas:


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuZ2FwbWluZGVyWyAsXCJjb250aW5lbnRcIl1cbmdhcG1pbmRlclsgLGMoXCJjb250aW5lbnRcIiwgXCJsaWZlRXhwXCIpXVxuYGBgIn0= -->

```r
gapminder[ ,"continent"]
gapminder[ ,c("continent", "lifeExp")]
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->



<!-- rnb-text-end -->

