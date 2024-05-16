PROCCES-RUN .PY

**Permite ver cómo cambia el estado de un proceso mientras se ejecuta en una CPU.**

RUNNING

READY

BLOCKED

DONE

La opción más importante para entender es **PROCESS_LIST** (especificada por los flags **-l** o **--processlist**), que especifica exactamente lo que hará cada programa en ejecución (o 'proceso'). Un proceso consta de instrucciones, y cada instrucción puede hacer una de dos cosas:

-   Usar la CPU
-   Emitir una E/S (y esperar a que se complete)

Ejemplo:

Aquí hay una ejecución simple que solo tiene un programa que se ejecuta y ese programa solo usa la CPU (no realiza ninguna E/S)

![image.png](https://i.postimg.cc/vHRbVW1P/image.png)


Aquí**, el proceso que especificamos es «5:100»,** lo que significa que debe constar de 5 instrucciones, y las probabilidades de que cada instrucción sea una instrucción de la CPU son del 100%.

![image.png](https://i.postimg.cc/1zYZ56hr/image.png)


**HOMEWORK**


1. Ejecute process-run.py con las siguientes banderas: -l 5:100,5:100. ¿Cuál debería ser la utilización de la CPU (por ejemplo, el porcentaje de tiempo que la CPU está en uso)? Utiliza las opciones-c y-p para comprobar si has acertado.

![image.png](https://i.postimg.cc/SNpbsk53/image.png)


2. Ahora ejecuta con estas banderas: ./process-run.py-l 4:100,1:0.  Estas banderas especifican un proceso con 4 instrucciones (todas para usar la CPU), y otro que simplemente emite una E/S y espera a que termine.

¿Cuánto tardan en completarse ambos procesos? Utiliza-c y-p  para saber si has acertado.

![image.png](https://i.postimg.cc/SN7FYHbs/image.png)


3. Cambia el orden de los procesos:-l 1:0,4:100. ¿Qué ocurre ahora? ¿Es importante cambiar el orden? ¿Por qué? (Como siempre, utiliza-c  y-para ver si tenías razón)

![image.png](https://i.postimg.cc/FKz2qRdd/image.png)

4.   Ahora exploraremos algunas de las otras banderas. Una bandera importante es-S, que determina cómo reacciona el sistema cuando un proceso es proceso realiza una E/S. Con la bandera fijada a SWITCH ON END, el sistema NO cambiará a otro proceso mientras uno está haciendo una E/S, en en lugar de esperar hasta que el proceso esté completamente terminado. ¿Qué ocurre cuando ejecuta los siguientes dos procesos (-l 1:0,4:100-c-SWITCH ON END), uno haciendo E/S y el otro haciendo trabajo de CPU?

**Flags**: **-S SWITCH_ON_END** configura el sistema para no cambiar de proceso mientras uno está haciendo E/S.

![image.png](https://i.postimg.cc/qByWWWRL/image.png)


5. Ahora, ejecute los mismos procesos, pero con el comportamiento de conmutación establecido para cambiar a otro proceso siempre que uno esté ESPERANDOI/O(-l 1:0,4:100-c-S SWITCH ON E/S). ¿Qué ocurre ahora? Utilice c  y -p para confirmar que has acertado.

![image.png](https://i.postimg.cc/m2SJgM71/image.png)

6. Otro comportamiento importante es qué hacer cuando finaliza una E/S. E/S. Con-I IO EJECUTAR LATER, cuando una E/S se completa, el proceso que la emitió no se ejecuta necesariamente de inmediato. proceso que la emitió no se ejecuta necesariamente de inmediato, sino que lo queque se estaba ejecutando en ese momento. ¿Qué ocurre cuando esta combinación de procesos? (./proceso-ejecutado.py-l 3:0,5:100,5:100,5:100-S SWITCH ON IO RUN IO-c-p-I LATER) ¿Se utilizan eficazmente los recursos del sistema?

![image.png](https://i.postimg.cc/CK96Q4pX/image.png)

7. Flags: -I IO_RUN_IMMEDIATE configura el sistema para ejecutar inmediatamente un proceso que completa una E/S.

![image.png](https://i.postimg.cc/kGmYnX4y/image.png)


8. Ahora ejecuta con algunos procesos generados aleatoriamente utilizando flags-s 1-l 3:50,3:50 o-s 2-l 3:50,3:50 o-s 3-l 3:50, 3:50. Comprueba si puedes predecir el resultado de la traza. ¿Qué ocurre ocurre cuando se utiliza bandera-I IO EJECUTAR f lag-I IO RUN INMEDIATA frente a la¿MÁS TARDE? ¿Qué ocurre cuando se utiliza la bandera-S SWITCH EN IO frente a-S SWITCH ON FIN?

![image.png](https://i.postimg.cc/59Bksv7K/image.png)

![image.png](https://i.postimg.cc/zXq26B4z/image.png)

![image.png](https://i.postimg.cc/X7x1bW0w/image.png)
