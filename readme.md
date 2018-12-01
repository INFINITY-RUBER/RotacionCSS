# C6 - Transformaciones de rotación

Para realizar las transformaciones de rotación utilizamos la función

```
    transform: rotate("grados"deg);
```

o mediante

```
    transform: rotate3d(boolX,boolY,boolZ, "grados"deg);
```

Existen diferentes formas de usar esta función de acuerdo a nuestras necesidades.

* Con valor positivo:
```
    transform: rotate(45deg);
```
* Con valor negativo:
```
    transform: rotate(-45deg);
```
* Rotando con respecto al eje X:
```
    transform: rotateX(45deg);
```
* Rotando con respecto al eje Y:
```
    transform: rotateY(45deg);
```
* Rotando con respecto al eje Z:
```
    transform: rotateZ(45deg);
```
* Concatenando transformaciones (Podemos usar mas de una transformación ademas de rotate)
```
    transform: rotateX(45deg) rotateZ(45deg);
```
* Usando los tres ejes de maneja conjunta (Simplificada)
```
    transform: rotate3d(1,1,0,45deg);
```

Para poder apreciar los cambios cuando usamos el transformaciones en el eje Z. En este caso _rotateZ("grados"deg)_ o _rotate3d(0,0,1, "grados"deg)_. Se debe especificar al navegador que estamos trabajando en un ambito 3D. Para comunicarle este dato usamos:

```
    perspective: "valor";
```

En ocasiones esto no sera suficiente. Ya que hay navegadores que requieren que se especifique este hecho cambiando ciertas propiedades. Tal es el caso de _Firefox_ donde ademas usamos:

```
    transform-style: perserve-3d;
```

Estas dos propiedades deben colocarse en el _elemento padre_ del elemento que contiene la animación.

En el caso de ***perspective*** tambien puede colocarse exclusivamente en aquellos elementos que hacen uso de un ambito 3D. La diferencia es que no se hara uso de este como propiedad, sino como función. Por ejemplo:

```
    transform: perspective(200px) rotateY(45deg);
```

Hay que tomar que encuenta, que usar ***perspective*** como propiedad (_perspective: "valor"_) o como función (_perspective("grados")_). Genera pequeñas diferencias en el resultado.