---
layout: post
title: 3DSCTF 2016 - Results Does Not Matter (PPC - level 1) 
description: Challenge Results Does Not Matter of 3DSCTF 2016
keywords: ppc, prog, rtfm, 3dsctf 2016, writeup
tags: [3DSCTF]
---
 
* **CTF:** 3DSCTF 2016 - <https://3dsctf.win>
* **Challenge:** Results Does Not Matter (PPC - level 1)
* **Author:** Eduardo EASH

****
> Description: 

Results does not matter!!!  
[EN]  
Santa got a paper with strange stuff on it.  
There was a hint on the bottom: "Use 32 bit"  
He have no idea what's this about.  
Can you help him to reveal the flag?  
Flag format: 3DS{sha256(FLAG)}  

[PT-BR]  
O papai Noel recebeu uma papel com um desenho estranho.  
No rodape estava escrito: "Use 32 bits"  
Ele nao faz a minima ideia do que se trata.  
Voce pode ajuda-lo?  
Flag no formato: 3DS{sha256(FLAG)}  


****

Temos o seguinte circuito:  
![Results Does Not Matter - 3DSCTF 2016 - EASHian Circuit :3](https://github.com/rtfm-ctf/rtfm-ctf.github.io/blob/master/assets/3DS_RESULTS_CHALL.PNG "Challenge")

O mestre EASH, aka: Papai Noel :3 nos disse que era para utilizar 32-bits, então limitaremos nosso brute conforme orientação superior (brutespace = 2 ^ 32). Montei um script em python a seguir para me ajudar a encontrar o valor correto que fornece a saída correta para que o circuito seja mais 1337) para a tão esperada flag.  

```python

"""
Solved by: RTFM[ChOkO]
"""

import hashlib

def sha256(x):
	hash_object = hashlib.sha256(x)
	hex_dig = hash_object.hexdigest()
	return hex_dig

n1 = 0x200 
n2 = 318
n3 = 0b1010001111100001000 ^ 334453
brutespace = 2 ** 32 
f1 = 0
f2 = 0
f3 = 0
sha = ''

for flag in xrange(brutespace):
	f1 = flag | n1
	f2 = f1 ^ n2
	f3 = f2 & n3
	#print "%s\t%s" % (flag,f3)
	if f3 == 1337:
		sha=sha256(str(flag))
		print '%s \t 3DS {\%s}' % (flag,sha)
                break
```  
