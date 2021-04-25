# Práctica 3 – MD5 en Erlang

En esta práctica vamos a reimplementar el cálculo de hashes md5 usando paso de mensajes.
El código proporcionado hace el cálculo usando un único proceso.

```
1> break_md5:break_md5s(["e80b5017098950fc58aad83c8c14978e",
"76a2173be6393254e72ffa4d6df1030a"]).
E80B5017098950FC58AAD83C8C14978E: abcdef
76A2173BE6393254E72FFA4D6DF1030A: passwd
ok
```

La barra de progreso corre en su propio proceso, y se imprime cada vez que recibe un mensaje
con los casos probados desde la última comunicación.

Partiendo de este código se pide:

## Ejercicio 1 (Haga el programa multiproceso)
Al igual que en la práctica anterior, modifica
la implementación para que el cálculo de los hashes se haga en multiples procesos. Cuando se
encuentre el password para un hash, hay que avisar al resto de procesos para que no lo continuen
comprobando. El programa debería parar cuando se hayan encontrado todos los passwords, es
decir, no debería quedar en ejecución ninguno de los procesos creados.

### Comprobación Finalización Procesos
Para comprobar la finalización correcta de los ficheros puede utilizarse el debugger, que se inicial
con `debugger:start().` A continuación seleccione los módulos de la práctica en `Module=>Interpret.`
Durante la ejecución del programa podrá ver los procesos que ejecutan código en esos módulos.
