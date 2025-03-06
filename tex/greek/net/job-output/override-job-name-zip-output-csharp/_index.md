---
title: Παράκαμψη ονόματος εργασίας και εγγραφή της εξόδου τερματικού σε Zip (C#)
linktitle: Παράκαμψη ονόματος εργασίας και εγγραφή της εξόδου τερματικού σε Zip (C#)
second_title: Aspose.TeX .NET API
description: Μάθετε πώς να παρακάμπτετε τα ονόματα εργασιών και να γράφετε την έξοδο τερματικού σε ένα αρχείο ZIP χρησιμοποιώντας το Aspose.TeX για .NET. Οδηγός βήμα προς βήμα με παραδείγματα C#.
weight: 11
url: /el/net/job-output/override-job-name-zip-output-csharp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Παράκαμψη ονόματος εργασίας και εγγραφή της εξόδου τερματικού σε Zip (C#)

## Εισαγωγή

Σε αυτό το σεμινάριο, θα διερευνήσουμε πώς να παρακάμψετε το όνομα εργασίας και να εγγράψετε την έξοδο τερματικού σε ένα αρχείο ZIP χρησιμοποιώντας το Aspose.TeX για .NET. Το Aspose.TeX είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να εργάζονται με έγγραφα TeX στις εφαρμογές τους .NET. Σε αυτό το συγκεκριμένο παράδειγμα, θα επικεντρωθούμε σε μια κοινή εργασία - τη σύνταξη της εξόδου τερματικού σε ένα αρχείο ZIP με τη δυνατότητα παράκαμψης του ονόματος εργασίας.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

- Γνώση εργασίας C#
- Εγκαταστάθηκε το Aspose.TeX για .NET
- Εισαγάγετε το αρχείο ZIP για τον κατάλογο εργασίας
- Έξοδος αρχείου ZIP για έξοδο τερματικού

## Εισαγωγή χώρων ονομάτων

Πριν βουτήξετε στον κώδικα, βεβαιωθείτε ότι έχετε συμπεριλάβει τους απαραίτητους χώρους ονομάτων στο έργο σας C#:

```csharp
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;
using System.IO;
```

Τώρα, ας αναλύσουμε το παράδειγμα σε πολλά βήματα για να σας καθοδηγήσουμε στη διαδικασία.

## Βήμα 1: Ανοίξτε τις ροές ZIP εισόδου και εξόδου

```csharp
using (Stream inZipStream = File.Open(Path.Combine("Your Input Directory", "zip-in.zip"), FileMode.Open))
using (Stream outZipStream = File.Open(Path.Combine("Your Output Directory", "terminal-out-to-zip.zip"), FileMode.Create))
{
    // Ο κώδικας για το βήμα 1 πηγαίνει εδώ
}
```

## Βήμα 2: Ορίστε τις επιλογές μετατροπής

```csharp
TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectTeX());
options.JobName = "terminal-output-to-zip";
options.InputWorkingDirectory = new InputZipDirectory(inZipStream, "in");
options.OutputWorkingDirectory = new OutputZipDirectory(outZipStream);
options.TerminalOut = new OutputFileTerminal(options.OutputWorkingDirectory);
```

## Βήμα 3: Καθορίστε τις επιλογές αποθήκευσης

```csharp
options.SaveOptions = new PdfSaveOptions();
```

## Βήμα 4: Εκτελέστε την εργασία TeX

```csharp
new TeXJob("hello-world", new PdfDevice(), options).Run();
```

## Βήμα 5: Ολοκληρώστε το αρχείο ZIP εξόδου

```csharp
((OutputZipDirectory)options.OutputWorkingDirectory).Finish();
```

## συμπέρασμα

Συγχαρητήρια! Μάθατε με επιτυχία πώς να παρακάμπτετε το όνομα της εργασίας και να γράφετε την έξοδο τερματικού σε ένα αρχείο ZIP χρησιμοποιώντας το Aspose.TeX για .NET. Αυτή η τεχνική μπορεί να είναι απίστευτα χρήσιμη όταν ασχολείστε με έγγραφα TeX στις εφαρμογές σας C#.

## Συχνές ερωτήσεις

### Ε1: Μπορώ να χρησιμοποιήσω το Aspose.TeX για .NET με άλλες γλώσσες .NET όπως το VB.NET;

A1: Ναι, το Aspose.TeX για .NET είναι συμβατό με όλες τις γλώσσες .NET.

### Ε2: Πού μπορώ να βρω περισσότερη τεκμηρίωση για το Aspose.TeX για .NET;

 A2: Επισκεφθείτε το[τεκμηρίωση](https://reference.aspose.com/tex/net/) για αναλυτικές πληροφορίες.

### Ε3: Πώς μπορώ να πάρω μια προσωρινή άδεια για το Aspose.TeX;

 A3: Λάβετε α[προσωρινή άδεια](https://purchase.aspose.com/temporary-license/) για δοκιμαστικούς σκοπούς.

### Ε4: Υπάρχει κάποιο φόρουμ κοινότητας για υποστήριξη Aspose.TeX;

 Α4: Ναι, εγγραφείτε[Φόρουμ Aspose.TeX](https://forum.aspose.com/c/tex/47) για κοινοτική υποστήριξη.

### Ε5: Πού μπορώ να αγοράσω το Aspose.TeX για .NET;

 A5: Μπορείτε να αγοράσετε Aspose.TeX[εδώ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
