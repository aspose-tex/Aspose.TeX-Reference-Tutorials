---
title: Set Metered License for Aspose.TeX in Java
linktitle: Set Metered License for Aspose.TeX in Java
second_title: Aspose.TeX Java API
description: 
type: docs
weight: 12
url: /java/managing-licenses/set-metered-license/
---

## Complete Source Code
```java
package com.aspose.tex.SetMeteredLicense;

public class SetMeteredLicense {
	public static void main(String[] args) throws Exception {
		// ExStart:SetMeteredLicense
		// Set metered public and private keys.
        new com.aspose.tex.Metered().setMeteredKey(
            "<type public key here>",
            "<type private key here>");
        // ExEnd:SetMeteredLicense
	}
}
```
