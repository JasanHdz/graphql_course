## ¿Qué es graphQL?

Es un nuevo paradigma aplicado a un problema antiguo que siempre han tenido los desarrolladores de tener que comunicar información entre diferentes aplicaciones, siempre se ha necesitado que una aplicación le envíe información a otra o que ejecute transformaciones en esa como tal, para ello se han creado diferentes tecnologías que han pasado de moda como por ejemplo: CORBA, SOAP, RPC que fueron remplazados de forma progresiva hasta llegar a la alternativa más reciente y más usada actualmente, **REST**.

Actualmente rest es la forma más usada para enviar y ejecutar transformaciones.

GraphQL se puede ver como una evolución a esté problema, fue creado por facebook en el 2015 por un problema que detectaron en su API Rest debido al volumen de información que ellos manejan, crearon una forma más flexible que les permitía con una sola consulta resolver lo que con muchas tenían que hacer en REST, entonces GraphQL se creó como un estandart que permite identificar de una forma más real como va ha ser usada una API, puede permitir una forma predicible de detectar todas las informaciones posibles con la información y viene con diferentes ventajas:

1. Lenguaje agóstico que me permite definir una forma clara y simple los objetos y acciones del API.
No importa del lenguaje al que quieras implementar tiene una base de lenguaje estandart diferente por si es Node.js, python, ruby.
2. una validación automática de la información al ingresar.
3. Control de errores de una manera uniforme y predectible.
- Documentación mínima autogenerada que permite saber exactamente cómo debe ser usada el API tanto a la hora de pedir y enviar información.
- Entorno de desarrollo amigable donde se puede probar todas las interacciones.

## Schema y types

La base de una api en graphQL es el Schema, el schema es un documento que escribe detalladamente todos los tipos de información que va ha tener el API, cada uno especificando que tipo de dato es.


## Queries y Resolvers

Una querie me permite ejecutar un request al API para obtener información como tál, tiene la caracteristica que yo debo pedir, cual es la consulta que deseo ejecutar y que campos de esa consulta deseo obtener.

Cuando envié lo siguiente en mi API va ha ir a ejecutar está consulta y va a devolver solamente esté campo
```json
{
  hero {
    name
  }
}
```

Esté es el formato en el que graphQl devuelve, siempre va ha ver un objeto que se llama data, que contiene la información que pedimos.

```json
{
  "data": {
    "hero": {
      "name": "R2-D2" 
    }
  }
}
```
Cuando yo quiera ejecutar una querie mágicamente no me va ha aparecer el resultado, necesitamos definir un objeto que se llama resolvers.

Importante notar que en los resolvers cada vez que yo defino una querie nueva necesito definir otro resolver para esa querie, y debe ser una función que me devuelva un valor.

## Custom Types

Ya que tenemos nuestra API en la web es hora de comenzar ha trabajar para tener una api funcional resolviendo un problema del mundo real en vez de tener un query que se está saludando, vamos a aprender ahora custom types y vamos a trabajar directamente en el código del schema 