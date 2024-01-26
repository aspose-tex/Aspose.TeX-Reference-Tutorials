---
title: Πληκτρολογήστε TeX σε XPS σε Java με εξωτερική ροή
linktitle: Πληκτρολογήστε TeX σε XPS σε Java με εξωτερική ροή
second_title: Aspose.TeX Java API
description: Μάθετε πώς να στοιχειοθετείτε TeX σε XPS σε Java χρησιμοποιώντας το Aspose.TeX. Εξερευνήστε βήμα προς βήμα οδηγίες για απρόσκοπτη επεξεργασία εγγράφων.
type: docs
weight: 10
url: /el/java/typesetting-tex-to-xps/typeset-tex-to-xps-external-stream/
---
## Εισαγωγή

Στον κόσμο της ανάπτυξης Java, το Aspose.TeX ξεχωρίζει ως ένα ισχυρό εργαλείο για τη στοιχειοθεσία εγγράφων TeX σε διάφορες μορφές, συμπεριλαμβανομένου του XPS. Αν θέλετε να βελτιώσετε τις δυνατότητες επεξεργασίας εγγράφων της εφαρμογής Java σας, αυτό το σεμινάριο είναι προσαρμοσμένο για εσάς. Σε αυτόν τον οδηγό βήμα προς βήμα, θα σας καθοδηγήσουμε στη διαδικασία στοιχειοθέτησης TeX σε XPS χρησιμοποιώντας Aspose.TeX για Java με εξωτερική ροή.

## Προαπαιτούμενα

Πριν ξεκινήσετε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

-  Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει Java στο σύστημά σας. Μπορείτε να το κατεβάσετε από[εδώ](https://www.oracle.com/java/technologies/javase-downloads.html).

-  Aspose.TeX για Java: Κατεβάστε και εγκαταστήστε το Aspose.TeX για Java. Μπορείτε να βρείτε τον σύνδεσμο λήψης[εδώ](https://releases.aspose.com/tex/java/).

## Εισαγωγή πακέτων

Ξεκινήστε εισάγοντας τα απαραίτητα πακέτα για να ξεκινήσετε το ταξίδι μετατροπής TeX σε XPS. Συμπεριλάβετε το ακόλουθο απόσπασμα κώδικα στο έργο σας Java:

```java
package com.aspose.tex.TypesetXpsWrittenToExternalStream;

import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStream;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## Βήμα 1: Διαμόρφωση επιλογών μετατροπής

Ξεκινήστε δημιουργώντας επιλογές μετατροπής για την προεπιλεγμένη μορφή ObjectTeX χρησιμοποιώντας τον ακόλουθο κώδικα:

```java
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

Αυτό θέτει τα θεμέλια για τη διαδικασία στοιχειοθεσίας.

## Βήμα 2: Καθορίστε το όνομα και τους καταλόγους εργασίας

Καθορίστε ένα όνομα εργασίας και ορίστε τους καταλόγους εργασίας εισόδου και εξόδου:

```java
options.setJobName("external-file-stream");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

Βεβαιωθείτε ότι έχετε αντικαταστήσει τα σύμβολα κράτησης θέσης όπως το "Ο Κατάλογος εισόδου σας" με τις πραγματικές διαδρομές καταλόγου σας.

## Βήμα 3: Διαμορφώστε την έξοδο τερματικού

Καθορίστε ότι η έξοδος του τερματικού θα πρέπει να γραφτεί σε ένα αρχείο στον κατάλογο εργασίας εξόδου:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

Αυτό το βήμα διασφαλίζει ότι καταγράφονται λεπτομερή αρχεία καταγραφής για εντοπισμό σφαλμάτων.

## Βήμα 4: Ανοίξτε τη ροή εξόδου

Ανοίξτε μια ροή για να γράψετε το στοιχειοθετημένο έγγραφο XPS:

```java
final OutputStream stream = new FileOutputStream("Your Output Directory" + options.getJobName() + ".xps");
```

Αντικαταστήστε το "Ο Κατάλογος εξόδου σας" με την κατάλληλη διαδρομή.

## Βήμα 5: Εκτελέστε την εργασία

Εκτελέστε την εργασία μετατροπής TeX σε XPS:

```java
try {
    new TeXJob("hello-world", new XpsDevice(stream), options).run();
} finally {
    stream.close();
}
```

Αυτό ολοκληρώνει τη διαδικασία και θα βρείτε το στοιχειοθετημένο έγγραφο XPS στον καθορισμένο κατάλογο εξόδου.

## συμπέρασμα

Συγχαρητήρια! Έχετε στοιχειοθετήσει με επιτυχία το TeX σε XPS σε Java χρησιμοποιώντας το Aspose.TeX. Αυτό ανοίγει έναν κόσμο δυνατοτήτων για επεξεργασία εγγράφων στις εφαρμογές σας Java. Πειραματιστείτε με διαφορετικά αρχεία TeX και εξερευνήστε τις διάφορες δυνατότητες που προσφέρει το Aspose.TeX.

## Συχνές ερωτήσεις

### Ε1: Μπορώ να χρησιμοποιήσω το Aspose.TeX για Java με άλλες μορφές εγγράφων;

A1: Το Aspose.TeX εστιάζει κυρίως στην επεξεργασία εγγράφων που σχετίζεται με το TeX. Για άλλες μορφές, εξερευνήστε την εκτεταμένη γκάμα προϊόντων της Aspose.

### Ε2: Υπάρχει διαθέσιμη δοκιμαστική έκδοση;

 A2: Ναι, μπορείτε να δοκιμάσετε το Aspose.TeX κατεβάζοντας τη δωρεάν δοκιμή[εδώ](https://releases.aspose.com/).

### Ε3: Πού μπορώ να βρω ολοκληρωμένη τεκμηρίωση;

 A3: Ανατρέξτε στην τεκμηρίωση[εδώ](https://reference.aspose.com/tex/java/) για λεπτομερείς πληροφορίες και παραδείγματα.

### Ε4: Πώς μπορώ να λάβω υποστήριξη ή να αναζητήσω βοήθεια;

 A4: Επισκεφθείτε το φόρουμ Aspose.TeX[εδώ](https://forum.aspose.com/c/tex/47)για κοινοτική υποστήριξη και συζητήσεις.

### Ε5: Μπορώ να αποκτήσω μια προσωρινή άδεια για σκοπούς δοκιμής;

 A5: Ναι, μπορείτε να αποκτήσετε μια προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/).