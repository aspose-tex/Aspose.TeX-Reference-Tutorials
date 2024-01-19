---
title: Typesetting TeX to XPS in .NET
linktitle: Typesetting TeX to XPS in .NET
second_title: Aspose.TeX .NET API
description: 
type: docs
weight: 10
url: /net/xps-output/typeset-tex-to-xps/
---

## Complete Source Code
```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;
using System.IO;

namespace Aspose.TeX.Examples.CSharp.TeXTypesetting
{
    /// <summary>
    /// Alternative way to obtain typeset document from XPS device.
    /// </summary>
    class TypesetXpsWrittenToExternalStream
    {
        public static void Run()
        {
            // ExStart:WriteOutputXpsToExternalStream
            // Create conversion options for default ObjectTeX format upon ObjectTeX engine extension.
            TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
            // Specify a job name.
            options.JobName = "external-file-stream";
            // Specify a file system working directory the for input.
            options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
            // Specify a file system working directory the for output.
            options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
            // Specify that the terminal output must be written to a file in the output working directory.
            // The file name is <job_name>.trm.
            options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);

            // Open the stream to write typeset XPS document. The file name is not necessarily the same as the job name.
            using (Stream stream = File.Open(Path.Combine("Your Output Directory", options.JobName + ".xps"), FileMode.Create))
                // Run the job.
                new TeXJob("hello-world", new XpsDevice(stream), options).Run();
            // ExEnd:WriteOutputXpsToExternalStream
        }
    }
}
```