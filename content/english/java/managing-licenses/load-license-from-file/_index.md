---
title: Load TeX License from File in Java
linktitle: Load TeX License from File in Java
second_title: Aspose.TeX Java API
description: 
type: docs
weight: 10
url: /java/managing-licenses/load-license-from-file/
---

## Complete Source Code
```java
package com.aspose.tex.LoadLicenseFromFile;

import com.aspose.tex.License;

public class LoadLicenseFromFile
{
	public static void main(String[] args) throws Exception
	{
		// ExStart:LoadLicenseFromFile
        // Initialize license object.
        License license = new License();
        // Set license.
        license.setLicense("D:\\Aspose.Total.Java.lic");
        System.out.println("License set successfully.");
        // ExEnd:LoadLicenseFromFile
	}
}
```
