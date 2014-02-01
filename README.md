Ejercicios-Tema5-Virtualización completa: uso de máquinas virtuales
===================================================================

####Antonio Melero Bello

###Ejercicio1

Instalar los paquetes necesarios para usar KVM. Se pueden seguir estas instrucciones. Ya lo hicimos en el primer tema, pero volver a comprobar si nuestro sistema está preparado para ejecutarlo o hay que conformarse con la paravirtualización.

En primer lugar hay que asegurarse de que nuestro procesador soporta la virtualizacion. 

    egrep -c '(vmx|svm)' /proc/cpuinfo
    
Para el cual hemos obtenido un resultado de 8 lo cual indica que si la soporta.

Despues comprobamos que esta activada la virtualización de S.O con el comando:

    kvm-ok
    
El resultado obtenido a sido:

    INFO: /dev/kvm exists \n
    KVM Aceleration can be used
    


###Ejercicio2

1.Crear varias máquinas virtuales con algún sistema operativo libre, Linux o BSD. Si se quieren distribuciones que ocupen poco espacio con el objetivo principalmente de hacer pruebas se puede usar CoreOS (que sirve como soporte para Docker) GALPon Minino, hecha en Galicia para el mundo, Damn Small Linux, SliTaz (que cabe en 35 megas) y ttylinux (basado en línea de órdenes solo).



###Ejercicio3

###Ejercicio4

###Ejercicio5

###Ejercicio6

###Ejercicio7


