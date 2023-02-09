# CyberCTF_Assignment_4

### 2. Challenge: Redaction gone wrong (Easy)

* The challenge requests to download a report and check for some critical data.
* The use of the tool “pdftotext” was usefull to manipulate the pdf contents on plain text.
* The script help us to get the flag hidden on the document:

		#!/bin/bash

		pdftotext -layout Financial_Report_for_ABC_Labs.pdf Financial_Report_for_ABC_Labs.txt
		cat Financial_Report_for_ABC_Labs.txt | grep pico > flag.txt

![R4_C2_1](https://user-images.githubusercontent.com/124681007/217745037-134c3900-f070-4aa5-92ad-ed396e9abf6b.png)

> The flag is: **“picoCTF{C4n_Y0u_S33_m3_fully}”**
