---
title: Stream Input, Image Output, and Terminal Input in Java
linktitle: Stream Input, Image Output, and Terminal Input in Java
second_title: Aspose.TeX Java API
description: 
type: docs
weight: 11
url: /java/advanced-io/stream-input-image-output/
---

## Complete Source Code
```java
package com.aspose.tex.StreamInputImageOutputAndTerminalInput;

import java.io.ByteArrayInputStream;
import java.io.IOException;

import com.aspose.tex.InputConsoleTerminal;
import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputConsoleTerminal;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.ImageDevice;
import com.aspose.tex.rendering.PngSaveOptions;

import util.Utils;

public class StreamInputImageOutputAndTerminalInput {
	public static void main(String[] args) throws IOException {
		Utils.setLicense();
		
		// ExStart:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
        // Create conversion options for default ObjectTeX format upon ObjectTeX engine extension.
        TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
        // Specify a job name.
        options.setJobName("stream-in-image-out");
        // Specify a file system working directory for the input.
        options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
        // Specify a file system working directory for the output.
        options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
        // Specify the console as the input terminal.
        options.setTerminalIn(new InputConsoleTerminal());  // Default value. Arbitrary assignment.
        // Specify the console as the output terminal.
        options.setTerminalOut(new OutputConsoleTerminal()); // Default value. Arbitrary assignment.

        // Define the saving options.
        PngSaveOptions pngOptions = new PngSaveOptions();
        pngOptions.setResolution(300);
        options.setSaveOptions(pngOptions);
        // Create the image device.
        ImageDevice device = new ImageDevice();
        // Run the job.
        TeXJob job = new TeXJob(new ByteArrayInputStream(
        		"\\hrule height 10pt width 95pt\\vskip10pt\\hrule height 5pt".getBytes("ASCII")),
                device, options);
        job.run();

        // When the console prompts the input, type "ABC", press Enter, then type "\end" and press Enter again.

        // For further output to look fine. 
        options.getTerminalOut().getWriter().newLine();

        // You can alternatively get images in form of array of byte arrays.
        // The first index for the page number (0-based, of course).
        byte[][] result = device.getResult();
        // ExEnd:TakeMainInputFromStream-AuxFromFileSystem-TakeTerminalInputFromConsole-AlternativeImagesStorage
	}
}
```
