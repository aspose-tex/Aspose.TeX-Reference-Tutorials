---
title: Παράκαμψη ονόματος εργασίας και εγγραφή εξόδου τερματικού σε Java
linktitle: Παράκαμψη ονόματος εργασίας και εγγραφή εξόδου τερματικού σε Java
second_title: Aspose.TeX Java API
description: Εξερευνήστε τον οδηγό βήμα προς βήμα σχετικά με την παράκαμψη ονομάτων εργασιών και τη σύνταξη εξόδου τερματικού χρησιμοποιώντας το Aspose.TeX για Java. Βελτιώστε την επεξεργασία των εγγράφων σας με ισχυρές επιλογές προσαρμογής.
weight: 10
url: /el/java/customizing-output/override-job-name-disk/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Παράκαμψη ονόματος εργασίας και εγγραφή εξόδου τερματικού σε Java

## Εισαγωγή

Το Aspose.TeX για Java παρέχει ισχυρές δυνατότητες για εργασία με αρχεία TeX, επιτρέποντας στους προγραμματιστές να χειρίζονται και να προσαρμόζουν την επεξεργασία εγγράφων TeX. Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία παράκαμψης του ονόματος εργασίας και εγγραφής της εξόδου τερματικού στο σύστημα αρχείων χρησιμοποιώντας το Aspose.TeX σε Java.

## Προαπαιτούμενα

Πριν ξεκινήσουμε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

- Γνώση προγραμματισμού Java.
-  Εγκαταστάθηκε το Aspose.TeX για Java. Μπορείτε να το κατεβάσετε από το[Τεκμηρίωση Aspose.TeX Java](https://reference.aspose.com/tex/java/).

## Εισαγωγή πακέτων

Για να ξεκινήσετε, εισαγάγετε τα απαραίτητα πακέτα στο έργο σας Java. Στο αρχείο Java, συμπεριλάβετε τις ακόλουθες εισαγωγές:

```java
package com.aspose.tex.OverridenJobNameAndTerminalOutputWrittenToDisk;

import java.io.IOException;

import com.aspose.tex.InputFileSystemDirectory;
import com.aspose.tex.OutputFileSystemDirectory;
import com.aspose.tex.OutputFileTerminal;
import com.aspose.tex.TeXConfig;
import com.aspose.tex.TeXJob;
import com.aspose.tex.TeXOptions;
import com.aspose.tex.rendering.XpsDevice;

import util.Utils;
```

## Παράκαμψη ονόματος εργασίας και εγγραφής εξόδου τερματικού

### Βήμα 1: Δημιουργία επιλογών μετατροπής

Ξεκινήστε δημιουργώντας επιλογές μετατροπής για την προεπιλεγμένη μορφή ObjectTeX στην επέκταση κινητήρα ObjectTeX. Χρησιμοποιήστε το ακόλουθο απόσπασμα κώδικα:

```java
//ExStart:OverrideJobName-WriteTerminalOutputToFileSystem
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectTeX());
```

### Βήμα 2: Καθορίστε το όνομα εργασίας και τους καταλόγους εργασίας

Καθορίστε ένα όνομα εργασίας, έναν κατάλογο εργασίας εισόδου και έναν κατάλογο εργασίας εξόδου. Εάν το όνομα εργασίας δεν έχει καθοριστεί, το πρώτο όρισμα του κατασκευαστή TeXJob θα ληφθεί ως όνομα εργασίας. Χρησιμοποιήστε το ακόλουθο απόσπασμα κώδικα:

```java
options.setJobName("overridden-job-name");
options.setInputWorkingDirectory(new InputFileSystemDirectory("Your Input Directory"));
options.setOutputWorkingDirectory(new OutputFileSystemDirectory("Your Output Directory"));
```

### Βήμα 3: Γράψτε την έξοδο τερματικού στο σύστημα αρχείων

 Καθορίστε ότι η έξοδος τερματικού πρέπει να εγγραφεί σε ένα αρχείο στον κατάλογο εργασίας εξόδου. Το όνομα του αρχείου θα είναι`<job_name>.trm`. Προσθέστε τον ακόλουθο κώδικα:

```java
options.setTerminalOut(new OutputFileTerminal(options.getOutputWorkingDirectory()));
```

### Βήμα 4: Εκτελέστε την εργασία

Εκτελέστε την εργασία TeX χρησιμοποιώντας τις καθορισμένες επιλογές και το όνομα εργασίας. Δείτε πώς μπορείτε να το κάνετε:

```java
TeXJob job = new TeXJob("hello-world", new XpsDevice(), options);
job.run();
// ExEnd:OverrideJobName-WriteTerminalOutputToFileSystem
```

Συγχαρητήρια! Έχετε παρακάμψει επιτυχώς το όνομα εργασίας και την έξοδο του τερματικού εγγραφής στο σύστημα αρχείων χρησιμοποιώντας το Aspose.TeX σε Java.

## συμπέρασμα

Σε αυτό το σεμινάριο, εξερευνήσαμε πώς να χρησιμοποιήσετε το Aspose.TeX για Java για να παρακάμψετε το όνομα της εργασίας και να καταγράψετε την έξοδο τερματικού. Αυτές οι δυνατότητες δίνουν στους προγραμματιστές τη δυνατότητα να έχουν λεπτό έλεγχο της επεξεργασίας εγγράφων TeX, ενισχύοντας την προσαρμογή και την ευελιξία.

## Συχνές ερωτήσεις

### Ε1: Μπορώ να χρησιμοποιήσω το Aspose.TeX για Java με άλλες βιβλιοθήκες Java;

A1: Ναι, το Aspose.TeX για Java έχει σχεδιαστεί για να ενσωματώνεται απρόσκοπτα με άλλες βιβλιοθήκες Java για να βελτιώσει τις δυνατότητες επεξεργασίας εγγράφων σας.

### Ε2: Πού μπορώ να βρω υποστήριξη για το Aspose.TeX για Java;

 A2: Επισκεφθείτε το[Φόρουμ Aspose.TeX](https://forum.aspose.com/c/tex/47) για υποστήριξη και βοήθεια της κοινότητας για τυχόν προβλήματα που μπορεί να αντιμετωπίσετε.

### Ε3: Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.TeX για Java;

 A3: Ναι, μπορείτε να έχετε πρόσβαση στη δωρεάν δοκιμαστική έκδοση του Aspose.TeX για Java[εδώ](https://releases.aspose.com/).

### Ε4: Πώς μπορώ να αποκτήσω μια προσωρινή άδεια χρήσης για το Aspose.TeX για Java;

 Α4: Ακολουθήστε αυτό[Σύνδεσμος](https://purchase.aspose.com/temporary-license/) για την απόκτηση προσωρινής άδειας για σκοπούς δοκιμών και αξιολόγησης.

### Ε5: Πού μπορώ να αγοράσω το Aspose.TeX για Java;

 A5: Επισκεφθείτε το[σελίδα αγοράς](https://purchase.aspose.com/buy) να αποκτήσει άδεια χρήσης για το Aspose.TeX για Java.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
