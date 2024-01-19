---
title: Load Aspose.TeX License from File (C#)
linktitle: Load Aspose.TeX License from File (C#)
second_title: Aspose.TeX .NET API
description: 
type: docs
weight: 10
url: /net/licensing/load-license-from-file-csharp/
---

## Complete Source Code
```csharp
using System;

namespace Aspose.TeX.Examples.CSharp.TeXTypesetting
{
    class LoadLicenseFromFile
    {
        public static void Run()
        {
            // ExStart:LoadLicenseFromFile
            // Initialize license object.
            License license = new License();
            // Set license.
            license.SetLicense("D:\\Aspose.Total.NET.lic");
            Console.WriteLine("License set successfully.");
            // ExEnd:LoadLicenseFromFile
        }
    }
}
```
