WHAT IS THIS?

Linux Kernel source code for the devices:

Leeco Le2(s2)
BUILD INSTRUCTIONS?

Specific sources are separated by releases with it's corresponding number. First, you should clone the project:

 

    $ mv s2_kernel
    $ cd s2_kernel
    $ git checkout tags/{release}
At the same level of the "kernel" directory:

Download a prebuilt gcc

    $ git clone https://android.googlesource.com/platform/prebuilts/gcc/linux-x86/arm/arm-eabi-4.9
Create KERNEL_OUT dir:

    $ mkdir KERNEL_OUT 
Your directory tree should look like this:

kernel
arm-eabi-4.9
KERNEL_OUT
Finally, build the kernel according the next table of product names:

device	product
s2 kernel	gohan
    $ make -C kernel  O=../KERNEL_OUT  ARCH=arm CROSS_COMPILE=../arm-eabi-4.9/bin/arm-eabi- s2_defconfig
    $ make O=../KERNEL_OUT/ -C kernel ARCH=arm  CROSS_COMPILE=../arm-eabi-4.9/bin/arm-eabi-                       
You can specify "-j CORES" argument to speed-up your compilation, example:

    $ make O=../KERNEL_OUT/ -C kernel ARCH=arm  CROSS_COMPILE=../arm-eabi-4.9/bin/arm-eabi- -j 8
