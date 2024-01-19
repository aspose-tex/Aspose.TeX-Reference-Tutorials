---
title: Create Custom TeX Formats for Consistent Typesetting in Java
linktitle: Create Custom TeX Formats for Consistent Typesetting in Java
second_title: Aspose.TeX Java API
description: 
type: docs
weight: 10
url: /java/custom-format/creating-custom-formats/
---

## Complete Source Code
```java
package com.aspose.tex.CustomTeXFormatFileCreation;

import java.io.IOException;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;

import util.Utils;

public class CustomTeXFormatFileCreation {
	public static void main(String[] args) throws IOException {
		Utils.setLicense();
		
		// ExStart:CreateCustomTeXFormatFile
        // Create TeX engine options for no format upon ObjectTeX engine extension.
        TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectIniTeX());
        // Specify a file system working directory for the input.
        options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
        // Specify a file system working directory for the output.
        options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));

        // Run format creation.
        TeXJob.createFormat("customtex", options);

        // For further output to look fine.
        options.getTerminalOut().getWriter().newLine();
        // ExEnd:CreateCustomTeXFormatFile
	}
}
```
