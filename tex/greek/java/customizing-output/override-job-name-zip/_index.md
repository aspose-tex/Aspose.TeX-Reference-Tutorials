---
title: Αντικαταστήστε το όνομα εργασίας και εγγράψτε την έξοδο τερματικού στο Zip σε Java
linktitle: Αντικαταστήστε το όνομα εργασίας και εγγράψτε την έξοδο τερματικού στο Zip σε Java
second_title: Aspose.TeX Java API
description: Μάθετε πώς να παρακάμπτετε τα ονόματα εργασιών και να γράφετε την έξοδο τερματικού σε ZIP σε Java με το Aspose.TeX. Ένα ολοκληρωμένο σεμινάριο για προγραμματιστές Java.
weight: 11
url: /el/java/customizing-output/override-job-name-zip/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Αντικαταστήστε το όνομα εργασίας και εγγράψτε την έξοδο τερματικού στο Zip σε Java

## Εισαγωγή

Στον κόσμο της ανάπτυξης Java, το Aspose.TeX ξεχωρίζει ως ένα ισχυρό εργαλείο για το χειρισμό μορφών αρχείων TeX. Σε αυτό το σεμινάριο, θα εμβαθύνουμε σε ένα συγκεκριμένο σενάριο – παράκαμψη ονομάτων εργασιών και εγγραφή της εξόδου τερματικού σε ένα αρχείο zip. Αυτός ο οδηγός βήμα προς βήμα θα σας καθοδηγήσει στη διαδικασία χρησιμοποιώντας το Aspose.TeX για Java.

## Προαπαιτούμενα

Πριν ξεκινήσουμε αυτό το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Βασικές γνώσεις προγραμματισμού Java.
-  Εγκατέστησε το Aspose.TeX για Java. Εάν όχι, μπορείτε να το κατεβάσετε από το[Aspose website](https://releases.aspose.com/tex/java/).
- Κατανόηση του τρόπου ρύθμισης ενός περιβάλλοντος ανάπτυξης Java.

## Εισαγωγή πακέτων

Ξεκινήστε εισάγοντας τα απαραίτητα πακέτα στο έργο σας Java. Αυτό διασφαλίζει ότι έχετε πρόσβαση στις λειτουργίες Aspose.TeX που απαιτούνται για την εργασία.

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToZip;

import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;

import com.aspose.tex.InputZipDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.OutputZipDirectory;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.PdfDevice;
import com.aspose.tex.rendering.PdfSaveOptions;

import util.Utils;
```

## Βήμα 1: Ανοίξτε τα αρχεία ZIP

Αρχικά, ανοίξτε μια ροή στο αρχείο ZIP που θα χρησιμεύσει ως κατάλογος εργασίας εισόδου. Αυτό είναι το αρχείο από το οποίο θα γίνει η επεξεργασία των δεδομένων σας.

```java
// Ανοίξτε μια ροή στο αρχείο ZIP εισόδου
final InputStream inZipStream = new FileInputStream("Your Input Directory" + "zip-in.zip");
```

## Βήμα 2: Ανοίξτε το Output ZIP Archive

Στη συνέχεια, ανοίξτε μια ροή σε ένα αρχείο ZIP που θα χρησιμεύσει ως ο κατάλογος εργασίας εξόδου. Εδώ θα γραφτεί η έξοδος του τερματικού.

```java
// Ανοίξτε μια ροή στο αρχείο ZIP εξόδου
final OutputStream outZipStream = new FileOutputStream("Your Output Directory" + "terminal-out-to-zip.zip");
```

## Βήμα 3: Ορίστε τις επιλογές μετατροπής

Δημιουργήστε επιλογές μετατροπής για την προεπιλεγμένη μορφή ObjectTeX κατά την επέκταση κινητήρα ObjectTeX. Καθορίστε ένα όνομα εργασίας και έναν κατάλογο εργασίας αρχείου ZIP τόσο για την είσοδο όσο και για την έξοδο.

```java
// Δημιουργήστε επιλογές TeX για τη μορφή ObjectTeX
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
options.setJobName("terminal-output-to-zip");
options.setInputWorkingDirectory(new InputZipDirectory(inZipStream, "in"));
options.setOutputWorkingDirectory(new OutputZipDirectory(outZipStream));
```

## Βήμα 4: Καθορίστε την έξοδο τερματικού

 Καθορίστε ότι η έξοδος τερματικού πρέπει να εγγραφεί σε ένα αρχείο στον κατάλογο εργασίας εξόδου. Το όνομα του αρχείου θα είναι`<job_name>.trm`.

```java
// Καθορίστε τις ρυθμίσεις εξόδου τερματικού
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

## Βήμα 5: Καθορίστε τις επιλογές αποθήκευσης και εκτελέστε την εργασία

Ορίστε επιλογές αποθήκευσης, όπως επιλογές αποθήκευσης PDF σε αυτήν την περίπτωση. Εκτελέστε την εργασία TeX για να εκτελέσετε τη μετατροπή.

```java
// Καθορίστε επιλογές αποθήκευσης και εκτελέστε την εργασία
options.setSaveOptions(new PdfSaveOptions());
new TeXJob("hello-world", new PdfDevice(), options).run();
```

## Βήμα 6: Ολοκληρώστε το αρχείο ZIP εξόδου

Αφού ολοκληρωθεί η εργασία, οριστικοποιήστε το αρχείο ZIP εξόδου για να διασφαλίσετε τη σωστή ολοκλήρωση.

```java
// Ολοκληρώστε το αρχείο ZIP εξόδου
((OutputZipDirectory) options.getOutputWorkingDirectory()).finish();
```

## συμπέρασμα

Συγχαρητήρια! Έχετε μάθει με επιτυχία πώς να παρακάμπτετε τα ονόματα εργασιών και να γράφετε την έξοδο τερματικού σε ένα αρχείο ZIP σε Java χρησιμοποιώντας το Aspose.TeX. Αυτή η ισχυρή λειτουργικότητα προσθέτει ευελιξία και αποτελεσματικότητα στα έργα ανάπτυξης Java.

## Συχνές ερωτήσεις

### Ε1: Τι είναι το Aspose.TeX;

A1: Το Aspose.TeX είναι μια βιβλιοθήκη Java που επιτρέπει στους προγραμματιστές να εργάζονται με μορφές αρχείων TeX, παρέχοντας προηγμένες λειτουργίες για την επεξεργασία εγγράφων.

### Ε2: Πώς μπορώ να αποκτήσω μια προσωρινή άδεια για το Aspose.TeX;

 A2: Μπορείτε να λάβετε μια προσωρινή άδεια από[αυτός ο σύνδεσμος](https://purchase.aspose.com/temporary-license/).

### Ε3: Πού μπορώ να βρω την τεκμηρίωση του Aspose.TeX;

 A3: Η τεκμηρίωση είναι διαθέσιμη[εδώ](https://reference.aspose.com/tex/java/).

### Ε4: Υπάρχει δωρεάν δοκιμαστική έκδοση του Aspose.TeX;

 A4: Ναι, μπορείτε να βρείτε τη δωρεάν δοκιμαστική έκδοση[εδώ](https://releases.aspose.com/).

### Ε5: Πού μπορώ να αναζητήσω υποστήριξη ή να κάνω ερωτήσεις σχετικά με το Aspose.TeX;

 A5: Επισκεφθείτε το[Φόρουμ Aspose.TeX](https://forum.aspose.com/c/tex/47) για υποστήριξη και συζητήσεις.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
