---
title: Override Job Name and Write Terminal Output to Disk (C#)
linktitle: Override Job Name and Write Terminal Output to Disk (C#)
second_title: Aspose.TeX .NET API
description: 
type: docs
weight: 10
url: /net/job-output/override-job-name-disk-output-csharp/
---

## Complete Source Code
```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Xps;

namespace Aspose.TeX.Examples.CSharp.TeXTypesetting
{
    /// <summary>
    /// Using file system directories for input and output, outputting to XPS device, overriding the job name, writing terminal output to disk.
    /// </summary>
    class OverridenJobNameAndTerminalOutputWrittenToDisk
    {
        public static void Run()
        {
            // ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
            // Create conversion options for default ObjectTeX format upon ObjectTeX engine extension.
            TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
            // Specify a job name. Otherwise, the first argument of the TeXJob constructor will be taken as a job name.
            options.JobName = "overriden-job-name";
            // Specify a file system working directory for the input.
            options.InputWorkingDirectory = new InputFileSystemDirectory("Your Input Directory");
            // Specify a file system working directory for the output.
            options.OutputWorkingDirectory = new OutputFileSystemDirectory("Your Output Directory");
            // Specify that the terminal output must be written to a file in the output working directory.
            // The file name is <job_name>.trm.
            options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);

            // Run the job.
            TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
            job.Run();
            // ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
        }
    }
}
```