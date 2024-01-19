---
title: Set Metered License for Aspose.TeX (C#)
linktitle: Set Metered License for Aspose.TeX (C#)
second_title: Aspose.TeX .NET API
description: 
type: docs
weight: 12
url: /net/licensing/set-metered-license-csharp/
---

## Complete Source Code
```csharp
namespace Aspose.TeX.Examples.CSharp.TeXTypesetting
{
    class SetMeteredLicense
    {
        public static void Run()
        {
            // ExStart:SetMeteredLicense
            // Set metered public and private keys.
            new Aspose.TeX.Metered().SetMeteredKey(
                "<type public key here>",
                "<type private key here>");
            // ExEnd:SetMeteredLicense
        }
    }
}

```
