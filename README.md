# 🚀 Proyecto de Laboratorio: Calculadora de Viajes Espaciales con funciones
## Fundamentos de Programación.
Autor: Fermín Cruz Mata. Adaptación: Alfonso Bengoa Díaz

¡Prepárate para una misión interplanetaria! En este laboratorio vas a construir una serie de scripts que simulan distintos aspectos de una misión espacial: cálculos de viaje, condiciones para realizar el viaje, y más.


---

## ⏱ Duración estimada

2 horas

---

## ✅ ¿Qué se practica?

- Tipos de datos: `float`, `int`, `str`, `bool`
- Entrada y salida
- Expresiones y operadores
- Condicionales `if` / `elif`
- Bucles `for` con `range()`
- Bucles `while`

---

## 📁 Archivos del proyecto

En primer lugar crea un proyecto Python denominado **L01_Viajes_espaciales** 
A continuacion, crea una carpeta `src` con los siguientes módulos Python:

``viajes_espaciales.py`` y ``test_viajes_espaciales.py``

✅ En el primer módulo se implementarán las siguientes funciones: 


```
- viaje_en_dias: Calcula la duración de viajes en días
- duracion_viaje: Calcula la duración con entradas de usuario (distancia y velocidad)
- puede_viajar: Comprobar si puedes embarcarte en la misión
- tiempos_viaje: Lista de tiempos para distintas velocidades (con for)
- simulacion_viaje: Repetir simulaciones (con while)
```
✅ En el segundo las funciones necesarias para hacer los test de los ejercicios implementados en el primer módulo.

---


## 📌 Ejercicio 1: Tiempo de viaje en días(`viaje_en_dias`)

La función recibe como parámetros la **distancia** en km, de tipo entero, y la **velocidad** en km/h tambíen de tipo entero y **devuelve el tiempo** (de tipo entero) en días que se tardaría en hacer un viaje de esa distancia a esa velocidad.

**Restricciones:** La distancia no puede ser negativa y la velocidad debe ser positiva. Si no se cumplen esta restricción la función devolverá **None**


**Recuerda que:**
- el tiempo es la distancia dividida por la velocidad pero en este ejercicio vamos a dividir con el operador **//** (parte entera) 
- que un día tiene 24 horas también se hará la división con el operador **//** (parte entera)

**Resultados esperados:**
```Python
-  Para una distancia de 384400 km (distancia Tierra - Luna) y una velocidad de 5000 km, la salida esperada es: "Se tardaría 3 días en llegar"

-  Si la función devuelve None,la salida esperada es: "La distancia debe ser mayor o igual que cero y la velocidad siempre mayor que cero"
```
---
## 📌 Ejercicio 2: Tiempo de viaje en días y fracción de días (`duracion_viaje`)

Se trata de implementar **la misma función del ejercicio anterior** y modificar lo necesario para que recibidendo la distancia y la velocidad, ambas de tipo entero, **devuelva el tiempo** de tipo `float`. 


**Resultados esperados:**
```Python
-  Para una distancia de 384400 km (distancia Tierra - Luna) y una velocidad de 5000 km, la salida esperada es: "Se tardaría 3.203333333333333 días en llegar"

-  Si la función devuelve None,la salida esperada es: "La distancia debe ser mayor o igual que cero y la velocidad siempre mayor que cero"
```



## 📌 Ejercicio 3: ¿Puedes viajar? (`puede_viajar`)

La función recibe como parámetros la **edad** y el **nivel físico** de un posible astronauta (de 1 a 10) y debe devolver una cadena con su condición para volar, según las siguientes reglas (usa la sentencia if para resolver el ejercicio).

- Edad < 18 → "Debes ser mayor de edad."
- Nivel físico < 5 → "Debes estar en mejor forma."
- Si cumple ambas: "¡Listo para despegar!"

**Restricciones:** La edad debe ser positiva y el nivel físico debe estar entre 1 y 10. Si no se cumplen estas restricciones la función devolverá **None**

**Resultados esperados:**
```Python
-  Segun los parámetros de entrada alguno de los tres siguientes mensajes:
  - "Condición del astronáuta: Debes ser mayor de edad."
  - "Condición del astronáuta: Debes estar en mejor forma."
  - "Condición del astronáuta: ¡Listo para despegar!"

-  Si la función devuelve None,la salida esperada es: "La edad debe ser positiva y el nivel físico entre 1 y 10"
```

---

## 📌 Ejercicio 4: Tabla de tiempos (`tiempos_viaje`)

La función recibe cuatro parámetros de tipo entero: **distancia, velocidad_inicia, velocidad_final y aceleración** e  invocado al ejercicio 2 (que recuerda que para una distancia y velocidad dada, devuelve el tiempo), debe crear y devolver **una lista de tuplas con las velocidades y los tiempos** que se tarda en recorrer la distancia dada.  En este ejercicio se presupone que los datos que se introducen en el test son consistentes entre ellos

**Ayudas**

La cabecera de la función es:

```python
def tiempos_viaje(distancia:int, v_ini:int, v_fin:int, aceleración:int)->list[tuple[int,float]]:
```
En el test debes recorrer la lista de tuplas que devuelve la función `tiempos_viaje`, (cada tupla tiene como primer elemento la velocidad y como segundo el tiempo) con un for:
```python
 tiempos = tiempos_viaje(distancia, vel_inicial, vel_final, aceleracion)
 for velocidad, tiempo in tiempos:
````
**Resultados esperados**


```python
Prueba por ejemplo, con una distancia 225 millones de km (distancia Tierra - Marte) con velocidades de 10.000 a 50.000 km/h, en saltos de 10.000 km/h (acelaración) la salida esperada será:

Velocidad: 10000 km/k -> Tiempo: 937.5 días
Velocidad: 20000 km/k -> Tiempo: 468.75 días
Velocidad: 30000 km/k -> Tiempo: 312.5 días
Velocidad: 40000 km/k -> Tiempo: 234.375 días
Velocidad: 50000 km/k -> Tiempo: 187.5 días
```

---

## 📌 Ejercicio 5: Repetir simulaciones (`simulacion_viaje`)

La función no recibe ni devuelve valor alguno, debe seguir, para repetir el número de simluaciones que se deseen, la siguiente secuencia: 

1. Pide por teclado que se introduzca la distancia y la velocidad con número enteros.
2. Invoca a la función ``duracion_viaje`` con sus respectivos parámetros y muestra el resultado: Para una distancia: **dddddd** y velocidad: **vvvvvv** el tiempo es: **tttttt**
3. Pregunta: "¿Quieres hacer otra simulación? (s/n)"
4. Si responde "s", repite desde el paso 1, 2 y 3. Si responde "n", termina el programa.

---
**Ayuda**
```python
Comienza inicializando una variable 'seguir' con el valor 's' que te permitirá mentener un bucle indefinido hasta que dicha variable la pongas a 'n' 
```

**Resultado esperado**

```Python
Introduce la distancia: 25000000
Introduce la velocidad: 60000
Para una distancia: 25000000 y velocidad: 60000 el tiempo es: 17.36111111111111
¿Quieres hacer otra simulación?(s/n): s

Introduce la distancia: 1000000
Introduce la velocidad: 11000
Para una distancia: 1000000 y velocidad: 11000 el tiempo es: 3.7878787878787876
¿Quieres hacer otra simulación?(s/n): s

Introduce la distancia: 384400
Introduce la velocidad: 5000
Para una distancia: 384400 y velocidad: 5000 el tiempo es: 3.203333333333333
¿Quieres hacer otra simulación?(s/n): n
```
