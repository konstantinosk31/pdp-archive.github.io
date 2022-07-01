---
layout: statement
codename: chef
---

Ο ιδιοκτήτης ενός Ιαπωνικού εστιατορίου θέλει να προσλάβει σεφ και θέλει τη βοήθειά σας. Το εστιατόριο είναι ανοιχτό κάθε βράδυ για $$N$$ ακριβώς λεπτά. Είναι γνωστό ότι κάθε σεφ μπορεί να ετοιμάσει μία μερίδα σούσι σε ακριβώς ένα λεπτό. Κάθε φορά που μία παραγγελία για μία νέα μερίδα φτάνει στην κουζίνα, οι σεφ σπεύδουν να την ετοιμάσουν. Αν όμως είναι ήδη απασχολημένοι λόγω φόρτου εργασίας από προηγούμενες παραγγελίες, τότε μπορεί να υπάρξουν καθυστερήσεις.

Ο ιδιοκτήτης έχει παρατηρήσει ότι αν ένας πελάτης χρειαστεί να περιμένει πάνω από $$D$$ λεπτά για μία παραγγελία του, τότε θα απογοητευτεί και θα φύγει χωρίς να πληρώσει. Θέλει λοιπόν να υπολογίσει ποιο είναι το ελάχιστο πλήθος από σεφ που πρέπει να δουλεύουν κάποιο βράδυ ώστε κανένας πελάτης να μην περιμένει περισσότερο από $$D$$ λεπτά. Για να το κάνει αυτό έχει στη διάθεσή του τις ακριβείς χρονικές στιγμές που γίνεται κάθε μία από τις $$M$$ παραγγελίες το συγκεκριμένο βράδυ.

Γράψτε ένα πρόγραμμα για να βοηθήσετε τον ιδιοκτήτη λύνοντας αυτό το πρόβλημα.

## Αρχεία Εισόδου (chef.in):

Η πρώτη γραμμή της εισόδου περιέχει $$3$$ θετικούς ακεραίους, το πλήθος $$N$$ των λεπτών που θα είναι ανοιχτό το εστιατόριο, τη μέγιστη καθυστέρηση $$D$$ που ανέχονται οι πελάτες και το πλήθος $$M$$ των παραγγελιών. Η δεύτερη γραμμή περιέχει ακριβώς $$M$$ θετικούς ακεραίους, ο $$i$$-οστός από τους οποίους είναι το λεπτό στο οποίο έγινε η $$i$$-οστή παραγγελία. Τα λεπτά είναι αριθμημένα από το $$1$$ μέχρι το $$N$$. Μπορείτε να υποθέσετε ότι καμία παραγγελία δεν θα γίνει μετά το λεπτό $$N – D$$.

## Αρχεία Εξόδου (chef.out):

Η έξοδος πρέπει να αποτελείται από μία γραμμή που περιέχει ακριβώς έναν ακέραιο αριθμό: το ελάχιστο πλήθος από σεφ που πρέπει να βρίσκονται στο εστιατόριο ώστε να εξυπηρετήσουν τους πελάτες χωρίς να χρειαστεί κανένας να περιμένει περισσότερο από $$D$$ λεπτά για να ετοιμαστεί η παραγγελία του.

## Παράδειγμα Αρχείου Εισόδου - Εξόδου:

| **chef.in**      | **chef.out** |
| :--- | :--- |
| 8 2 12<br>1 2 4 2 1 3 5 6 2 3 6 4 | 2 |


**Εξήγηση παραδείγματος**: Με δύο σεφ μπορούμε να εξυπηρετήσουμε όλες τις παραγγελίες ως εξής: Στο πρώτο λεπτό, ετοιμάζουν την 1η και την 5η παραγγελία οι οποίες έχουν καθυστέρηση $$0$$ (είναι έτοιμες στο τέλος του πρώτου λεπτού). Στο δεύτερο λεπτό, ετοιμάζουν την 2η και την 4η παραγγελία, κι αυτές με καθυστέρηση $$0$$. Στο 3ο λεπτό, ετοιμάζουν την 9η (με καθυστέρηση $$1$$) και την 6η (με καθυστέρηση $$0$$). Στο 4ο λεπτό, ετοιμάζουν την 10η (καθυστέρηση $$1$$) και την 12η (καθυστέρηση $$0$$). Στο 5ο λεπτό, την 3η (καθυστέρηση $$1$$) και την 7η (καθυστέρηση $$0$$). Τέλος, στο 6ο λεπτό ετοιμάζουν την 8η και την 11η παραγγελία (καθυστέρηση $$0$$). Στο 7ο και στο 8ο λεπτό, οι σεφ δεν έχουν παραγγελίες να ετοιμάσουν. Με λιγότερους από $$2$$ σεφ δεν θα ήταν εφικτό να εξυπηρετήσουμε όλους τους πελάτες χωρίς καθυστέρηση πάνω από $$2$$ σε κάποια παραγγελία.

## Περιορισμοί

 - $$1 \leq N \leq 100.000$$.
 - $$0 \leq D < N$$.
 - $$1 \leq M \leq 1.000.000$$.
 - Όριο χρόνου εκτέλεσης: $$1$$ sec.
 - Όριο μνήμης: $$64$$ MB.