---
date: 2026-09-04
description: Μάθετε πώς να ορίσετε μια metered license σε Java για το Aspose.TeX,
  να διαμορφώσετε public and private keys και να ξεκλειδώσετε το full feature set
  της βιβλιοθήκης.
keywords:
- how to set license
- configure public private keys
- Aspose.TeX metered license
lastmod: 2026-09-04
linktitle: Ορισμός Metered License για το Aspose.TeX σε Java
og_description: Πώς να ορίσετε άδεια για το Aspose.TeX σε Java. Αυτός ο οδηγός σας
  δείχνει πώς να διαμορφώσετε public and private keys, να ενεργοποιήσετε μια metered
  license και να αρχίσετε να χρησιμοποιείτε αμέσως τις full TeX processing capabilities.
og_image_alt: Screenshot of Java code initializing Aspose.TeX metered license
og_title: Πώς να ορίσετε άδεια για το Aspose.TeX σε Java
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to set a metered license in Java for Aspose.TeX, configure
    public and private keys, and unlock the library’s full feature set.
  headline: How to set license for Aspose.TeX in Java
  type: TechArticle
- questions:
  - answer: Yes, the metered keys are not tied to a specific device; each usage counts
      toward your overall quota.
    question: Can I use the same keys on multiple machines?
  - answer: The library throws a `LicenseException`. Purchase additional usage or
      upgrade your plan to continue processing.
    question: What happens if I exceed my metered quota?
  - answer: Call it once during initialization (for example, in a static block or
      the `main` method) so the license is globally available.
    question: Do I need to call `setMeteredKey` on every application start?
  - answer: Yes, the same code works on any Java runtime that can load the Aspose.TeX
      JAR, including Android apps.
    question: Is the metered license compatible with both Java SE and Android?
  - answer: After invoking `setMeteredKey`, execute any Aspose.TeX API (e.g., render
      a simple document). If no `LicenseException` is thrown, the license is active.
    question: How do I verify that the license was applied correctly?
  type: FAQPage
second_title: Aspose.TeX Java API
title: Πώς να ορίσετε άδεια για το Aspose.TeX σε Java
url: /el/java/managing-licenses/set-metered-license/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να ορίσετε άδεια για το Aspose.TeX σε Java

## Εισαγωγή

Σε αυτόν τον οδηγό θα μάθετε **πώς να ορίσετε άδεια** για το Aspose.TeX κατά την ανάπτυξη εφαρμογών Java. Η ρύθμιση μιας μετρημένης άδειας αφαιρεί όλους τους περιορισμούς αξιολόγησης, σας δίνει πρόσβαση σε κάθε API απόδοσης, μετατροπής και επεξεργασίας, και σας επιτρέπει να εργάζεστε εντελώς εκτός σύνδεσης. Θα καλύψουμε τις προαπαιτήσεις, τον ακριβή κώδικα που πρέπει να επικολλήσετε, και τις κοινές παγίδες ώστε να ξεκινήσετε χωρίς σφάλματα άδειας.

## Σύντομες απαντήσεις
- **Τι κάνει η “set metered license java”;** Καταχωρεί τα δημόσια και ιδιωτικά κλειδιά σας στο Aspose.TeX, ενεργοποιώντας τη χρήση όλων των λειτουργιών και τη χρέωση βάσει χρήσης.  
- **Χρειάζομαι σύνδεση στο διαδίκτυο;** Όχι. Αφού οριστούν τα κλειδιά, η βιβλιοθήκη λειτουργεί εντελώς εκτός σύνδεσης.  
- **Ποια κλειδιά απαιτούνται;** Ένα δημόσιο κλειδί και ένα ιδιωτικό κλειδί που παρέχονται με τη μετρημένη άδεια του Aspose.TeX.  
- **Μπορώ να αλλάξω τα κλειδιά αργότερα;** Ναι—καλέστε ξανά το `Metered.setMeteredKey` με τις νέες τιμές.  
- **Είναι αυτή η προσέγγιση ασφαλής για νήματα;** Η κλάση `Metered` διαχειρίζεται την ταυτόχρονη εκτέλεση εσωτερικά, ώστε να μπορείτε να την αρχικοποιήσετε με ασφάλεια μία φορά κατά την εκκίνηση της εφαρμογής.

## Τι είναι το “set metered license java”;

Η φόρτωση μιας μετρημένης άδειας ενημερώνει το runtime του Aspose.TeX ποιο όριο χρήσης ανήκει στον λογαριασμό σας. Παρέχοντας τα δημόσια και ιδιωτικά κλειδιά, η βιβλιοθήκη μπορεί να παρακολουθεί πόσα έγγραφα TeX επεξεργάζεστε και να επιβάλλει τα όρια που ορίζονται στο μετρημένο σας πλάνο. Αυτή η άμεση καταχώρηση είναι το μοναδικό βήμα που απαιτείται για να ξεκλειδώσετε όλες τις premium λειτουργίες.

## Γιατί να ορίσετε μια μετρημένη άδεια για το Aspose.TeX;

Μια μετρημένη άδεια σας παρέχει άμεση, απεριόριστη πρόσβαση σε **όλες τις 30+ επιλογές απόδοσης** και επιτρέπει στη μηχανή να επεξεργάζεται αρχεία TeX έως **200 σελίδες** χωρίς να φορτώνει ολόκληρο το έγγραφο στη μνήμη. Επίσης ενεργοποιεί χρέωση βάσει χρήσης, ώστε να πληρώνετε μόνο για τα έγγραφα που πραγματικά μετατρέπετε. Επειδή η άδεια αποθηκεύεται τοπικά, δεν υπάρχει **καμία εξωτερική εξάρτηση σε χρόνους εκτέλεσης**, κάτι που βελτιώνει την αξιοπιστία και μειώνει την καθυστέρηση σε περιβάλλοντα υψηλής απόδοσης.

## Προαπαιτήσεις

- Περιβάλλον ανάπτυξης Java (JDK 8 ή νεότερο) και ένα εργαλείο κατασκευής όπως Maven ή Gradle.  
- Μία έγκυρη μετρημένη άδεια Aspose.TeX που περιλαμβάνει ένα **δημόσιο κλειδί** και ένα **ιδιωτικό κλειδί**. Εάν δεν έχετε ακόμη, αποκτήστε την από [Aspose Purchase](https://purchase.aspose.com/buy).  
- Το JAR του Aspose.TeX προστέθηκε στο classpath του έργου σας. Μπορείτε να κατεβάσετε το πιο πρόσφατο πακέτο από τη [release page](https://releases.aspose.com/tex/java/).

Τώρα που έχετε όλα έτοιμα, ας προχωρήσουμε στην υλοποίηση.

## Εισαγωγή πακέτων

Προσθέστε το namespace του Aspose.TeX στο αρχείο πηγαίου κώδικα Java ώστε ο μεταγλωττιστής να μπορεί να εντοπίσει τις κλάσεις αδειοδότησης.

```java
package com.aspose.tex.SetMeteredLicense;
```

## Πώς να ορίσετε μετρημένη άδεια Java

`Metered` είναι η κλάση Aspose.TeX που αποθηκεύει και επικυρώνει τα δημόσια και ιδιωτικά κλειδιά για μια μετρημένη άδεια.  
`setMeteredKey` είναι μια στατική μέθοδος που καταχωρεί τα παρεχόμενα κλειδιά στο runtime.

Μπορείτε να ενεργοποιήσετε μια μετρημένη άδεια με μόνο δύο γραμμές κώδικα. Καλέστε τη στατική μέθοδο `setMeteredKey` στην κλάση `Metered`, περνώντας τα δημόσια και ιδιωτικά κλειδιά που λάβατε από το Aspose. Αυτή η κλήση πρέπει να τοποθετηθεί σε έναν στατικό αρχικοποιητή ή στο κύριο σημείο εισόδου ώστε να εκτελείται μία φορά ανά εκκίνηση του JVM.

### Βήμα 1: Εισαγωγή της κλάσης Aspose.TeX `Metered`

`Metered` είναι η κεντρική κλάση που αποθηκεύει και επικυρώνει το ζεύγος δημόσιου/ιδιωτικού κλειδιού για μια μετρημένη άδεια. Εξασφαλίζει επίσης ότι οι έλεγχοι άδειας εκτελούνται με ασφαλή τρόπο για νήματα σε όλη την εφαρμογή.

```java
// Import the Aspose.TeX package
import com.aspose.tex.Metered;
```

### Βήμα 2: Ορισμός δημόσιου και ιδιωτικού κλειδιού

Εδώ πραγματικά **ορίζετε δημόσιο και ιδιωτικό κλειδί** χρησιμοποιώντας την κλάση `Metered`. Αντικαταστήστε τις συμβολοσειρές placeholder με τα ακριβή κλειδιά που παρέχονται στο email της άδειας σας. Μην προσθέτετε επιπλέον κενά ή αλλαγές γραμμής, καθώς η διαδικασία επικύρωσης απαιτεί ακριβή αντιστοιχία.

```java
// Set metered public and private keys
new Metered().setMeteredKey(
    "<type public key here>",
    "<type private key here>"
);
```

Μόλις εκτελεστεί αυτός ο κώδικας, κάθε επόμενη κλήση στο API του Aspose.TeX θα λειτουργεί υπό το αδειοδοτημένο σας όριο χωρίς να ρίχνει εξαιρέσεις άδειας.

## Συνηθισμένες παγίδες και λύσεις

- **Ξεχάσατε να προσθέσετε τη βιβλιοθήκη στο classpath** – Ο κώδικας μεταγλωττίζεται αλλά ρίχνει `ClassNotFoundException` σε χρόνο εκτέλεσης. Βεβαιωθείτε ότι το JAR του Aspose.TeX αναφέρεται στο Maven `pom.xml`, Gradle `build.gradle` ή στο χειροκίνητο classpath.  
- **Χρήση λανθασμένης μορφής κλειδιού** – Τα κλειδιά πρέπει να είναι ακριβείς συμβολοσειρές που παρέχονται από το Aspose. Επιπλέον κενά, αλλαγές γραμμής ή ελλιπείς χαρακτήρες θα προκαλέσουν σφάλμα άδειας.  
- **Κλήση του `setMeteredKey` πολλές φορές** – Παρόλο που το API το επιτρέπει, κάθε κλήση προσθέτει μικρό κόστος επικύρωσης. Αρχικοποιήστε την άδεια μία φορά κατά την εκκίνηση (π.χ., σε static block) και χρησιμοποιήστε την καθ' όλη τη διάρκεια της εφαρμογής.

## Συχνές ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω τα ίδια κλειδιά σε πολλαπλές μηχανές;**  
Α: Ναι, τα μετρημένα κλειδιά δεν είναι δεσμευμένα σε συγκεκριμένη συσκευή· κάθε χρήση μετράει προς το συνολικό σας όριο.

**Ε: Τι συμβαίνει αν υπερβώ το μετρημένο όριο μου;**  
Α: Η βιβλιοθήκη ρίχνει `LicenseException`. Αγοράστε επιπλέον χρήση ή αναβαθμίστε το πλάνο σας για να συνεχίσετε την επεξεργασία.

**Ε: Χρειάζεται να καλέσω το `setMeteredKey` σε κάθε εκκίνηση της εφαρμογής;**  
Α: Καλέστε το μία φορά κατά την αρχικοποίηση (π.χ., σε static block ή στη μέθοδο `main`) ώστε η άδεια να είναι διαθέσιμη παγκοσμίως.

**Ε: Είναι η μετρημένη άδεια συμβατή με Java SE και Android;**  
Α: Ναι, ο ίδιος κώδικας λειτουργεί σε οποιοδήποτε runtime Java που μπορεί να φορτώσει το JAR του Aspose.TeX, συμπεριλαμβανομένων των εφαρμογών Android.

**Ε: Πώς μπορώ να επαληθεύσω ότι η άδεια εφαρμόστηκε σωστά;**  
Α: Μετά την κλήση του `setMeteredKey`, εκτελέστε οποιοδήποτε API του Aspose.TeX (π.χ., αποδώστε ένα απλό έγγραφο). Αν δεν ριχτεί `LicenseException`, η άδεια είναι ενεργή.

**Ε: Μπορώ να μεταβώ από μια μετρημένη άδεια σε μια διαρκή άδεια αργότερα;**  
Α: Απόλυτα. Αντικαταστήστε την κλήση `Metered.setMeteredKey` με την τυπική αρχικοποίηση της κλάσης `License` χρησιμοποιώντας το αρχείο διαρκούς άδειας σας.

**Ε: Υπάρχει κάποιος αντίκτυπος στην απόδοση όταν χρησιμοποιείται μια μετρημένη άδεια;**  
Α: Η επικύρωση της άδειας γίνεται μόνο μία φορά ανά εκκίνηση του JVM και προσθέτει λιγότερο από 5 ms επιπλέον χρόνο, κάτι που είναι αμελητέο για τις περισσότερες εφαρμογές.

## Συμπέρασμα

Τώρα γνωρίζετε **πώς να ορίσετε άδεια** για το Aspose.TeX σε Java, από την προετοιμασία του περιβάλλοντος μέχρι την κλήση του `Metered.setMeteredKey` με τα δημόσια και ιδιωτικά σας κλειδιά. Με την άδεια ενεργή, μπορείτε να αξιοποιήσετε πλήρως το εκτενές σύνολο λειτουργιών του Aspose.TeX — απόδοση, μετατροπή και επεξεργασία εγγράφων TeX — χωρίς περιορισμούς χρόνου εκτέλεσης.

---

**Last Updated:** 2026-09-04  
**Tested With:** Aspose.TeX 24.0 for Java  
**Author:** Aspose

## Σχετικά Μαθήματα

- [Managing Licenses](/tex/java/managing-licenses/)
- [Java License Management: How to Set License from File](/tex/java/managing-licenses/load-license-from-file/)
- [Load License From Stream](/tex/java/managing-licenses/load-license-from-stream/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}