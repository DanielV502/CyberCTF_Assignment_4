# CyberCTF_Assignment_4

### 3. Challenge: Safe Opener (Medium)

* The challenge requests to download a report and check for some critical data.
* The use of the tool “jd-gui” was useful to manipulate the pdf contents on plain text.
* The script help us to get the flag hidden on the document:

		#!/bin/bash

		cat KeygenMe.java | grep -oE "'.'" | tac | tr -d "\n" | tr -d "'" > flag.txt

![R4_C3_1](https://user-images.githubusercontent.com/124681007/217746085-b6ff4e17-9eac-42ca-85d4-9208b7bc2162.png)

> The flag is: **“picoCTF{700l1ng_r3qu1r3d_738cac89}”**
