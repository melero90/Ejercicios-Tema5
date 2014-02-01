Ejercicios-Tema5-Virtualización completa: Uso de máquinas virtuales
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

    INFO: /dev/kvm exists
    KVM Aceleration can be used
    

###Ejercicio2

1.Crear varias máquinas virtuales con algún sistema operativo libre, Linux o BSD. Si se quieren distribuciones que ocupen poco espacio con el objetivo principalmente de hacer pruebas se puede usar CoreOS (que sirve como soporte para Docker) GALPon Minino, hecha en Galicia para el mundo, Damn Small Linux, SliTaz (que cabe en 35 megas) y ttylinux (basado en línea de órdenes solo).

2. Hacer un ejercicio equivalente usando otro hipervisor como Xen, VirtualBox o Parallels.

He usado VirtualBox para instalar Debian 7.3. Aquí muestro algunas capturas del proceso de configuración, instalación y de la máquina virtual funcionando:

![imagen1](https://dl.dropbox.com/s/z0sfoz9z3x1pz98/idebian1.png)

![imagen2](https://dl.dropbox.com/s/tujsjqqbaktt0yi/idebian2.png)

![imagen3](https://dl.dropbox.com/s/bvyxfd010pfgp2d/instalandodebian2.png)

![imagen4](https://dl.dropbox.com/s/y3krkz79gplrek6/debiancorriendo.png)


###Ejercicio3

###Ejercicio4

###Ejercicio5

###Ejercicio6

###Ejercicio7


