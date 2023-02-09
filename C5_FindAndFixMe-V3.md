# CyberCTF_Assignment_4

### 5. Challenge: FindAndFixMe-V3.pdf (Hard)

* The challenge requests to fix a provided PDF file:
	* Hint: Eventually, You need to run the program and guess the password!
* The inspection of the file gave us an error that guided the analysis to check for the headers of the ZIP file.
* We can confirm that the file was altered with PDF file type values.
* The hex values have to be restored to the original file type with a Hex Editor in order to open the ZIP file:
	* **“50 4B 03 04 means ASCII translation of PK”**

![R4_C5_1](https://user-images.githubusercontent.com/124681007/217748874-e4bdd901-2a43-4a24-bd60-e1fa9ecb35ca.png)

![R4_C5_2](https://user-images.githubusercontent.com/124681007/217748888-78d921c5-f372-4373-a388-c9c989baa994.png)

* We can now use some reverse engineering on the code to understand what it does and work with the Fernet Cryptography’s Module to extract the password we require using python:

		from cryptography.fernet import Fernet

		K1=b'EAeeFGJDUZEeaishu4qaxswNUmKcmTDn1HjrKYN8U7Y='
		K2=b'gAAAAABjDLCIjp7gZPdLEynEO0XaCNusDgM5jjUkKQ7hoXLGIQq4t5UoQw9WmsgAup3XlBkqkwWhgsQM7qYuj3piy0xpRfQnh4F6Pa6XOkXimrH9gjtQnphSnri_3q8Y6oshPIcz9rbgl1CVjCpEGEi3DPRS5Oe-CstC_CNQG-pDFmU255PeksQdMWNI2v9e3Ugy22hwB8ndgW6H3jNTZ89ru5DH-MUKLFMwcYEKQtQhC3XlAwJaOXwU_WZ5X9TMbV1ODBChm-taN8T2V0pU8hx9Yji5brVHfgUfXGcAdGZKGJItMpixYZ0ISvnBvHB04bWNwlf1eBMmG_3Jpl33SerrCCIe4OfOPpB2ktRbhDceppl6mlnwbfo75ZZAMNbqP3RRK2-eWjFEKY47GTf2pN6KMKW6V2s3nK9lZpP4FLPVJ16OsuPLd8Q6NrcKwt2o5sYPA54M3fb22-4U6hQhkmVgJ_m24SHRCw=='
		muHa = "bAF0rTG5AY2PMO86AtOzvcqDxibbRyfIAJ38rzvOxZVsSp6!WBi7QvOSHSd3Lz4BtpSePA6jn9Kdcqfrodr4YjP9fdgkGOBjD!N6CLOvEkyvwTx8DAlFSyFHdbOMfeWZpMEyxRbYy1hgat2EOqZLoGgemWhBCynRj2tpijuTacdMXZYNctDx8PbSI8FHS5fNdQPVvVWiYnQouUxEWHNYVpNkmyyBUTB4PzvWhLulUVTy4gulGhzgRLVydgPD3zbu3GlwwWjD2v7itpPBBVz3skHqmmx6MAOskoc7oP90fRq1BW2cA01f1jAST3UQdryVT8x3iBzYfRToFnpKMRVfmJtQRNlkHv0av1onhjSpLUChop5rwPxXTUWEUHLrrIwIxUO1mAr2TpKAjr1rEycue4f1uL7QQ2MPBpzMxFDe6qjU0ytEkWjRFZahlO20CJDsMl4VcVjqo4gyOCaONTQwZuRqClv9yDZQIodTqZj0NZXK5fF5tGn8RP$AU45u#TR?as3"
		KEY = Fernet(K1)

		#To get the decripted code
		print(KEY.decrypt(K2).decode())
		print("     Decrypted password: "+muHa[100]+muHa[200]+muHa[300]+muHa[400]+muHa[500]+muHa[250]+muHa[125]+muHa[75]+muHa[50]+muHa[25])

* We can run the decode and decrypt functions to get the program’s password:

> The password is: **“CYBERPedii”**
