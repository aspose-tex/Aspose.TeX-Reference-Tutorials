---
title: Load Aspose.TeX License from Stream (C#)
linktitle: Load Aspose.TeX License from Stream (C#)
second_title: Aspose.TeX .NET API
description: 
type: docs
weight: 11
url: /net/licensing/load-license-from-stream-csharp/
---

## Complete Source Code
```csharp
using System;
using System.IO;

namespace Aspose.TeX.Examples.CSharp.TeXTypesetting
{
    class LoadLicenseFromStream
    {
        public static void Run()
        {
            // ExStart:LoadLicenseFromStream
            // Initialize license object.
            License license = new License();
            // Load license in FileStream.
            FileStream myStream = new FileStream("D:\\Aspose.Total.NET.lic", FileMode.Open);
            // Set license.
            license.SetLicense(myStream);
            Console.WriteLine("License set successfully.");
            // ExEnd:LoadLicenseFromStream
        }
    }
}
```
