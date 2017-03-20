---
layout: post
title: AusCERT 2015 - F0RG0TT3NP@$$W0RD (Forensics - 200 poins) 
description: Challenge F0RG0TT3NP@$$W0RD of AusCERT 2015 CTF
keywords: ppc, prog, rtfm, auscert 2015, warlock gam3z, writeup
tags: [AusCERT]
---

* **CTF:** AusCERT 2015 CTF
* **Challenge:** F0RG0TT3NP@$$W0RD (level 2)
* **Category:** Forensics
* **Author:** warl0ck gam3z
* **Solved by:** RTFM[ChOkO] 
****  

>Description: Our network administrator built this system last night but had to leave before documenting some data.  
I need you to find a few things for us.  
Downloaded here.  
Password: f0rg0tMyP@$$w0rd@g@!n.  
Please review and fill in the details here   
****  

Realizamos o download do arquivo e fizemos sua extração com a senha fornecida na descrição:  
[!extracting](https://ctf-br.org/wp-content/uploads/2015/06/extract.png "extract")  
 
O arquivo Build-2102.vmem trata-se de um arquivo de paginação de memória do VMware Worksation com cerca de 1.0 Gb de tamanho e composto de mais de 4 milhões de linhas. Para adquirirmos a flag, necessitamos fornecer dados corretos na página de verificação (https://warl0ck.gam3z.com/auscert/wgzCh3ck3r.aspx?accesscode=f0rg0tt3np@$$w0rd), que solicita 3 valores, respectivamente: Username, Password e Message.

Analisamos as strings do dump de memória da VMware filtrando pela palavra “t0k3n”, o que nos retorna 5 resultados. Como necessitamos de três valores, analisamos as palavras contidas antes e depois das ocorrências de t0k3n e uma tripla nos chama a atenção:  
[!flag](https://ctf-br.org/wp-content/uploads/2015/06/flag1-1024x341.png "Flag")  

Após algumas tentativas, inserimos os valores destacados acima na página de verificação e obtemos a flag para este nível.

* FLAG: th3 t0k3n y0u s33k: bfdea73bf7bc2d04ac565fd61113fa4f
