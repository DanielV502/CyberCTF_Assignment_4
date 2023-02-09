# CyberCTF_Assignment_4

### 1. Challenge: Safe Opener (Easy)

* The challenge request to recover a lost key from a java program.
* Opening the “SafeOpener.java” file, gave us the row where the key is stored.

![R4_C1_1](https://user-images.githubusercontent.com/124681007/217743130-162be5e9-c44d-4f92-b096-6bcaffdc3b39.png)

* By extracting the encoded key and decoding it with base64 we get the flag:

> The flag is: **“picoCTF{ pl3as3_l3t_m3_1nt0_th3_saf3}”**

* Whit a script we can automate the process to get the flag with a couple of lines of code:

		#!/bin/bash

		Flag=$(cat ./SafeOpener.java | grep "String encodedkey ="  | cut -d "\"" -f2 | cut -d "\"" -f1 | base64 -d)
		echo "picoCTF{"$Flag"}" > flag.txt

![R4_C1_2](https://user-images.githubusercontent.com/124681007/217743141-12307f7a-a530-4806-8db7-833f85d93929.png)
