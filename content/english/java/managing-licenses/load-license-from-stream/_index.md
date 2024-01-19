---
title: Load TeX License from Stream in Java
linktitle: Load TeX License from Stream in Java
second_title: Aspose.TeX Java API
description: 
type: docs
weight: 11
url: /java/managing-licenses/load-license-from-stream/
---

## Complete Source Code
```java
package com.aspose.tex.LoadLicenseFromStream;

import java.io.FileInputStream;
import java.io.InputStream;

import com.aspose.tex.License;

public class LoadLicenseFromStream
{
	public static void main(String[] args) throws Exception
	{
		// ExStart:LoadLicenseFromStream
        // Initialize license object.
        License license = new License();
        // Load license in FileStream.
        InputStream myStream = new FileInputStream("D:\\Aspose.Total.Java.lic");
        // Set license.
        license.setLicense(myStream);
        System.out.println("License set successfully.");
        // ExEnd:LoadLicenseFromStream
	}
}
```
