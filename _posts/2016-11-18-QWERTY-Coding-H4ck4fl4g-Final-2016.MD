---
layout: post
title: QWERTY - H4ck4fl4g  Final 2016
description: Challenge QWERTY of H4ck4fl4g Final 2016
keywords: qwerty, codingm H4ck4fl4g, Final, 2016,
tags: [H4ck4fl4g]
---

* **CTF:** H4ck4fl4g Final 2016
* **Challenge:** QWERTY
* **Category:** Coding
* **Author:** Gabriel "AstuteJoe" Garcia
* **Solved by:** RTFM[ChOkO] 

****  
>Description: Um erro comum de digitação nas mensagens é digitar a tecla ao lado. Você deve decodificar 5 mensagens onde as letras estão trocadas pelas letras a sua esquerda. (Exemplo.. W por Q e K por J) Obs: Só existem letras maiúsculas e espaços e a letra Z é mapeada para o L e A para P e Q para M. IP: 172.16.10.31 PORTA: 3031    
****  


```python
import socket
import time

def traduz(x):
    msg = ''
    dict = {'Q' : 'W', 'W' : 'E', 'E' : 'R', 'R' : 'T', 'T' : 'Y', 'Y' : 'U', 'U' : 'I', 'I' : 'O', 'O' : 'P', 'P' : 'A', 'A' : 'S', 'S' : 'D', 'D' : 'F', 'F' : 'G', 'G' : 'H', 'H' : 'J', 'J' : 'K', 'K' : 'L', 'L' : 'Z', 'Z' : 'X', 'X' : 'C', 'C' : 'V', 'V' : 'B', 'B' : 'N', 'N' : 'M', 'M' : 'Q', ' ' : ' '}

    for i in x:
        if i == None:
            pass
        else:
            msg += dict.get(i)
    return msg

host = "import socket
import time

def traduz(x):
    msg = ''
    dict = {'Q' : 'W', 'W' : 'E', 'E' : 'R', 'R' : 'T', 'T' : 'Y', 'Y' : 'U', 'U' : 'I', 'I' : 'O', 'O' : 'P', 'P' : 'A', 'A' : 'S', 'S' : 'D', 'D' : 'F', 'F' : 'G', 'G' : 'H', 'H' : 'J', 'J' : 'K', 'K' : 'L', 'L' : 'Z', 'Z' : 'X', 'X' : 'C', 'C' : 'V', 'V' : 'B', 'B' : 'N', 'N' : 'M', 'M' : 'Q', ' ' : ' '}

    for i in x:
        if i == None:
            pass
        else:
            msg += dict.get(i)

    return msg

host = "127.0.0.1"
port=3031
s = socket.socket(socket.AF_INET,socket.SOCK_STREAM)
s.connect((host,port))
chall = ''
#for i in xrange(6):
while not 'DESEC' in chall:
    chall = s.recv(1024).strip()
    #print '[DEBUG] chall = %s' % chall
    print '[<] %s' % chall
    response = traduz(chall)
    response = response.rstrip()
    s.send(response+'\n')
    print '[>] %s' % response
    print '------------------------------'
    time.sleep(1)
```
