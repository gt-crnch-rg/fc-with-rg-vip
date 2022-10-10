_Last updated: 10/22/21_

## Why should I care about paths?
When working with Linux systems, PATH and library paths, such as LD_LIBRARY_PATH and LIBRARY_PATH, are usually critical for correctly compiling large codebases. In many cases, systems without modules may also have multiple versions of a library or compiler, and you need to pick between one. 

* PATH - refers to your application execution path. Referred to by $PATH
* LIBRARY_PATH - specifies to a compiler which directories to search to find static and shared libraries that are _linked_ with an executable at compile-time. 
* LD_LIBRARY_PATH - used by the executable at _runtime_ to search for shared libraries (DLLs in Windows). These runtime dependencies can often be checked using `ldd <executable>` for a dynamically linked executable.
```
# Print out the dynamically loaded libraries needed to run this application
$ ldd mpi_hello_world
        linux-vdso64.so.1 =>  (0x00007fffaa9d0000)
        libmpi.so.12 => /usr/lib64/openmpi/lib/libmpi.so.12 (0x00007fffaa880000)
        libpthread.so.0 => /lib64/libpthread.so.0 (0x00007fffaa820000)
        libc.so.6 => /lib64/libc.so.6 (0x00007fffaa630000)
```

### What are some useful commands to know?
* env - prints out *all* your environment variables. Best combined with grep to find a specific environment variable. 
```
#Print it all out!
[]$env
XDG_SESSION_ID=1946
TERM=xterm
SHELL=/bin/bash
SSH_TTY=/dev/pts/1
USER=jyoung
LD_LIBRARY_PATH=
...

#More scoped env call looking for OpenCL environments
[]$env | grep OCL
INTELFPGAOCLSDKROOT=/export/tools/reconfig/intel/18.1/hld
```
* echo - print out the current path or other environment variable
```
[]$echo $PATH
/usr/local/bin:/usr/bin:/usr/local/sbin:/usr/sbin:/usr/lib64/openmpi/bin:/usr/local/cuda/bin:/nethome/jyoung
```
* export - set an environment variable like. Note that you need to include your old path to avoid overwriting it. 
```
[]$echo $PATH
/usr/bin:/usr/sbin
#Tell tools to look in /usr/local/bin before looking in /usr/bin
export PATH=/usr/local/bin:$PATH
/usr/local/bin:/usr/bin:/usr/sbin
```

## Python paths
Python can have its own issues in terms of loading modules, especially when multiple installations of Python are available on a system. An error like ` import pyopencl._cl as _cl ImportError: ImportError: numpy.core.multiarray failed to import` often (but not always) means that there is a conflict amongst different Python installations and where their imports are installed. 

The most important environment variable to check is PYTHONPATH. It is not recommended to use PYTHONHOME unless you really understand how your installation is loading modules.

* [Master list of Python environment variables](https://docs.python.org/3/using/cmdline.html#environment-variables)

## More advanced path and linking topics
Linux tools like ldconfig can be used to build a cache or dynamically loaded libraries. Please read [here](https://linux.101hacks.com/unix/ldconfig/) for more details. 
