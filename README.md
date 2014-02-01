Ejercicios-Tema5-Virtualización completa: Uso de máquinas virtuales
===================================================================

####Antonio Melero Bello

###Ejercicio1

**Instalar los paquetes necesarios para usar KVM. Se pueden seguir estas instrucciones. Ya lo hicimos en el primer tema, pero volver a comprobar si nuestro sistema está preparado para ejecutarlo o hay que conformarse con la paravirtualización.**

En primer lugar hay que asegurarse de que nuestro procesador soporta la virtualizacion. 

    egrep -c '(vmx|svm)' /proc/cpuinfo
    
Para el cual hemos obtenido un resultado de 8 lo cual indica que si la soporta.

Despues comprobamos que esta activada la virtualización de S.O con el comando:

    kvm-ok
    
El resultado obtenido a sido:

    INFO: /dev/kvm exists
    KVM Aceleration can be used
    
Una vez comprobamos esto procedemos a instalar los paquetes mediante la siguiente orden:

    sudo apt-get install qemu-kvm qemu-system libvirt-bin virtinst virt-manager
    
![imageninstalacion](https://dl.dropbox.com/s/6xt5qk9w5a96m3k/instalandoej1.png)
    

###Ejercicio2

**1.Crear varias máquinas virtuales con algún sistema operativo libre, Linux o BSD. Si se quieren distribuciones que ocupen poco espacio con el objetivo principalmente de hacer pruebas se puede usar CoreOS (que sirve como soporte para Docker) GALPon Minino, hecha en Galicia para el mundo, Damn Small Linux, SliTaz (que cabe en 35 megas) y ttylinux (basado en línea de órdenes solo).**

El primer paso es activar el modulo de virtualizacion

    sudo modprobe kvm-intel
    
Vamos a instalar un SO ligero, [ttylinux](http://ttylinux.net/). Para ello nos descargamos una de las [imagenes](http://ttylinux.net/dloadV-x86_64.html), creamos un disco duro virtual y la lanzamos con quemu.

    qemu-img create -f raw ttylinuxhdd.img 100M
    qemu-system-x86_64 -hda ttylinuxhdd.img -cdrom ttylinux-virtio_x86_64-16.1.iso -show-cursor
    
![ttylinux](https://dl.dropbox.com/s/tikqctdr59vqcou/ttylinux.png)

**2. Hacer un ejercicio equivalente usando otro hipervisor como Xen, VirtualBox o Parallels.**

He usado VirtualBox para instalar Debian 7.3. Aquí muestro algunas capturas del proceso de configuración, instalación y de la máquina virtual funcionando:

![imagen1](https://dl.dropbox.com/s/z0sfoz9z3x1pz98/idebian1.png)

![imagen2](https://dl.dropbox.com/s/tujsjqqbaktt0yi/idebian2.png)

![imagen3](https://dl.dropbox.com/s/bvyxfd010pfgp2d/instalandodebian2.png)

![imagen4](https://dl.dropbox.com/s/y3krkz79gplrek6/debiancorriendo.png)


###Ejercicio3

Crear un benchmark de velocidad de entrada salida y comprobar la diferencia entre usar paravirtualización y arrancar la máquina virtual simplemente con qemu-system-x86_64 -hda /media/Backup/Isos/discovirtual.img

###Ejercicio4

**Crear una máquina virtual Linux con 512 megas de RAM y entorno gráfico LXDE a la que se pueda acceder mediante VNC y ssh.**

[LXDE](http://es.wikipedia.org/wiki/LXDE) es un entorno de escritorio libre para Unix. El nombre se corresponde a "Lightweight X11 Desktop Environment", que en español significaría algo como "Entorno de escritorio X11 ligero". Podemos ver las [distribuciones](http://es.wikipedia.org/wiki/LXDE#Distribuciones_GNU.2FLinux_con_LXDE) que lo usan.

Vamos a instalar [Lubuntu](http://es.wikipedia.org/wiki/Lubuntu) que es la que más me ha llamado la atención. Lo podemos hacer desde su [página oficial](https://help.ubuntu.com/community/Lubuntu/GetLubuntu) en la sección Downloads.

Al igual que en el ejercicio 2.1:

    qemu-img create -f qcow2 lubuntuhdd.img 10G
    qemu-system-x86_64 -hda hdd.img -cdrom lubuntu-12.04-desktop-amd64.iso -m 512M
    
![imagen5](https://dl.dropbox.com/s/k5pi17ujqsxbcp7/Lubuntu_Install.png)

![imagen6](https://dl.dropbox.com/s/073ffbg1ocv5fvi/lubuntu.png)


###Ejercicio5

###Ejercicio6

###Ejercicio7


