# Sistema de filtrado para los resultados y aplicacion de _debouncing_ en la busqueda

Autores:

- @carlosbritto32
- @Hermestech

## 1 TL;DR

Se propone hacer un sistema de filtrado de resultados para el buscador de la app de la siguiente manera:
instalar axios (que es un cliente HTTP basado en promesas) y utilizarlo para tomar la data de la API que vamos a consumir. Despues de tener lista la data debemos mostrar en una lista desplegable las opciones que coincidan con lo que este escribiendo el usuario en la barra de busqueda, para que encuentre el lugar que esta buscando de manera rapido. Y debemos aplicar debouncing porque esperamos ver los resultados de filtrado en tiempo real, para evitar que nuestra app se pause o deje de responder cuando el usuario este escribiendo en el input de navegacion, porque pueden existir miles o millones de lugares en la API que va a consumir nuestra app

## 2 Motivación

Queremos desarrollar un sistema que sea veloz confiable, y sobre todo que le muestre todo de manera concreta a nuestro usuario, para que encuentre los lugares que este buscando de manera eficaz.

## 3 Propuesta de implementación

C1
![](https://github.com/carlosbritto32/RFC-FilterAndDebouncing/blob/main/img/C1.drawio.png)

C2
![](https://github.com/carlosbritto32/RFC-FilterAndDebouncing/blob/main/img/C2.PNG)

C3
![](https://github.com/carlosbritto32/RFC-FilterAndDebouncing/blob/main/img/C3.drawio.png)

## 4 Métricas

No aplica

## 5 Riesgos e inconvenientes

- El principal riesgo es que si no logramos realizar una busqueda eficiente, podemos crashear nuestra app.
- la busqueda puede ser muy lenta
- mala experiencia del usuario

## 6 Alternativas

- podemos usar fetch en lugar de axios

## 7 Impacto potencial y dependencias

- Al mostrarse en el home impactamos la UI
- impacta el backend, y la base de datos de lugares

## 8 Preguntas sin resolver

Como va a ser la consistencia de la base de datos y si la busqueda debe ser key sensitive.

## 9 Conclusión

El debouncing es importante para nuestra search bar, debido a que brinda una buena experiancia de uso para nuestro usuario.
