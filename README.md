# Install QEMU

sudo apt update \
sudo apt install qemu \
git clone git://github.com/mit-pdos/xv6-public.git \
make \
make qemu-noxCopy 

Here are the steps: 

**Step 1** – Install qemu: 
$ sudo apt install qemuCopy \
If you have 64 bit OS there is a chance Makefile will not be able to find qemu. In that case you should edit the Makefile at line 54 and add the following code: 

QEMU = qemu-system-x86_64Copy \

**Step 2** – Install xv6

- Create a directory, and clone xv6 to that directory: \
$ git clone git://github.com/mit-pdos/xv6-public.gitCopy 

**Step 3** – Compile xv6 \
$ makeCopy 

**Step 4** – Compile and run the emulator qemu: 
$ make qemuCopy \
The emulator will start but it will echo on the terminal too. Better to run it with the following frag (preferred): \
$ make qemu-noxCopy \
Also, for gdb enabled execution run: \
$ make qemu-nox-gdbCopy \
To enter the qemu console at any time, press ctrl+a, then c. If you want to exit, simply type “quit” to exit the emulator

**Step 5** – Write an user application (eg: bla)
5.1) Create a copy of an existent program like wc and name it as your new user program (eg bla.c):\
$ cp wc.c bla.cCopy\
5.2) Edit bla.c with your favorite editor. Take a look at the source code examples of existent commands, in order to see the syntax of the available functions of xv6 (they are slightly different).\
5.3) Modify the makefile of xv6 to include bla.c: The simplest way is to open the makefile, search for wc and add bla next to it whenever it appears on the makefile\
5.4) Clean and recompile xv6.\
The new command should be available.
