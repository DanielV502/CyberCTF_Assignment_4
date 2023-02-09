# CyberCTF_Assignment_4

### 4. Challenge: SQLiLite (Medium)

* The challenge requests to login on a Website.

![R4_C4_1](https://user-images.githubusercontent.com/124681007/217747519-bc48cbf1-d6aa-4ade-a9e2-dc6117c61b35.png)

![R4_C4_2](https://user-images.githubusercontent.com/124681007/217747534-0ab078db-effb-450f-99e7-ffa701b47291.png)

![R4_C4_3](https://user-images.githubusercontent.com/124681007/217747538-06660f4f-3897-44d8-ac8a-891732450001.png)

* The SQL Injection Attack used the payload **“' OR 1==1 --”** to modify the SQL query at the login validation and grant us access to the site where the flag is hidden:

> The flag is: **“picoCTF{L00k5_l1k3_y0u_solv3d_it_9b0a4e21}”**
