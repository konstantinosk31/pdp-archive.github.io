---
layout: statement
codename: erasmus
---

Το πρόγραμμα Erasmus (Σχέδιο δράσης της Ευρωπαϊκής Ένωσης για την κινητικότητα των φοιτητών) είναι πρόγραμμα ανταλλαγής φοιτητών της Ευρωπαϊκής Ένωσης (ΕΕ) που δημιουργήθηκε το $$1987$$. Το **Erasmus+** είναι το νέο πρόγραμμα που συνδυάζει όλα τα τρέχοντα προγράμματα της *ΕΕ* για την εκπαίδευση, την κατάρτιση, τη νεολαί και τον αθλητισμό, και άρχισε τον Ιανουάριο του $$2014$$. Τα τμήματα Μηχανικών Η/Υ και Πληροφορικής των Ελληνικών Πανεπιστημίων συνεργάστηκαν προκειμένου να αυξηθούν οι επιλογές των φοιτητών τους. Για το σκοπό αυτό πέρα από την κοινή ενημέρωση ανέπτυξαν κοινή πλατφόρμα υποβολής αιτήσεων των ενδιαφερομένων φοιτητών και ενιαία μοριοδότηση.

## Πρόβλημα

Να αναπτύξετε ένα πρόγραμμα σε μια από τις γλώσσες του *IOI (PASCAL, C, C++, Java)* το οποίο, αφού διαβάσει τις προσφερόμενες από τα πανεπιστήμια θέσεις, τα μόρια και τις προτιμήσεις όλων των ενδιαφερομένων φοιτητών, θα υλοποιεί την επιλογή των φοιτητών στα πανεπιστήμια. Η επιλογή πρέπει να είναι δίκαιη: κάθε φοιτητής θα πρέπει να επιλέγεται στο πανεπιστήμιο που βρίσκεται όσο το δυνατόν ψηλότερα στις προτιμήσεις του, υπό την προϋπόθεση όμως ότι οι θέσεις σε αυτό δεν έχουν καλυφθεί από φοιτητές που έχουν συγκεντρώσει περισσότερα μόρια. Είναι πιθανό κάποιοι φοιτητές να μην επιλεγούν σε καμία θέση και είναι πιθανό κάποιες προσφερόμενες θέσεις να μείνουν κενές.

## Αρχεία Εισόδου:
Τα αρχεία εισόδου με όνομα **erasmus.in** είναι αρχεία κειμένου με την εξής δομή: Στην πρώτη γραμμή υπάρχουν δύο ακέραιοι αριθμοί $$Ν$$ και $$M$$, χωρισμένοι μεταξύ τους με ένα κενό διάστημα: το πλήθος $$N$$ των πανεπιστημίων που προσφέρουν θέσεις και το πλήθος $$M$$ των φοιτητών που υπέβαλαν αίτηση. Στη δεύτερη γραμμή υπάρχουν ακριβώς $$Ν$$ ακέραιοι αριθμοί $$X_i$$ (όπου $$1 \leq i \leq N$$): το πλήθος των θέσεων που προσφέρει κάθε πανεπιστήμιο. Κάθε μία από τις επόμενες $$Μ$$ γραμμές αντιστοιχεί σε έναν ενδιαφερόμενο φοιτητή και αποτελείται από $$3$$ έως $$12$$ αριθμούς χωρισμένους ανά δύο με ένα κενό διάστημα: $$B, K, \Pi_1, \Pi_2, \ldots, \Pi_K$$, όπου $$B$$ το πλήθος των μορίων που συγκεντρώνει ο φοιτητής, $$K$$ το πλήθος των πανεπιστημίων που προτιμά ($$1 \leq K \leq 10$$) και $$\Pi_1, \Pi_2, \ldots, \Pi_K$$ οι κωδικοί αριθμοί των πανεπιστημίων που προτιμά, κατά φθίνουσα σειρά προτίμησης. Θεωρούμε ότι τα πανεπιστήμια είναι αριθμημένα από $$1$$ μέχρι και $$Ν$$.

## Αρχεία Εξόδου:
Τα αρχεία εξόδου με όνομα **erasmus.out** είναι αρχεία κειμένου με την εξής δομή. Περιέχουν ακριβώς $$Μ$$ γραμμές, μία για κάθε ενδιαφερόμενο φοιτητή με τη σειρά που αυτοί δίνονται στο αρχείο εισόδου. Κάθε γραμμή περιέχει είτε τη λέξη «NONE», αν ο φοιτητής δεν έχει επιλεγεί σε κανένα πανεπιστήμιο, είτε τον κωδικό αριθμό του πανεπιστημίου στο οποίο επιλέγεται ο φοιτητής.

## Περιορισμοί:
* $$1 \leq Ν \leq 1000$$,
* $$1 \leq Μ \leq 10.000$$,
* $$1 \leq X_i \leq 100$$,
* $$1 \leq B \leq 20.000$$,
* Δεν υπάρχουν δύο φοιτητές που να έχουν συγκεντρώσει το ίδιο πλήθος μορίων.
* Δεν υπάρχει φοιτητής που να έχει δηλώσει το ίδιο πανεπιστήμιο δύο φορές στη λίστα προτιμήσεών του.

## Παραδείγματα Αρχείων Εισόδου - Εξόδου:



**1<sup>o</sup>**

| **erasmus.in**      | **erasmus.out** |
| :--- | :--- |
| 3 3 <br> 1 1 1 <br> 170 2 1 3 <br> 180 1 2 <br> 175 3 2 1 3 | 3 <br> 2 <br> 1 |

Στο πρώτο παράδειγμα υπάρχουν $$3$$ πανεπιστήμια, από τα οποία προσφέρει μόνο μία θέση. Υποβλήθηκαν $$3$$ αιτήσεις. Ο πρώτος φοιτητής με $$170$$ μόρια δήλωσε ως πρώτη προτίμηση το πανεπιστήμιο με κωδικό $$1$$ και ως δεύτερη προτίμηση το πανεπιστήμιο με κωδικό $$3$$. Ο δεύτερος φοιτητής δήλωσε ως μοναδική προτίμηση το πανεπιστήμιο με κωδικό $$2$$. Ο τρίτος φοιτητής δήλωσε και τα τρία πανεπιστήμια, κατά σειρά: $$2$$, $$1$$, και $$3$$. Ο δεύτερος φοιτητής, με τα περισσότερα μόρια, επιλέγεται για το πανεπιστήμιο με κωδικό $$2$$ που είναι η μοναδική του προτίμηση. Ο  τρίτος  φοιτητής  επιλέγεται  για  το πανεπιστήμιο  με κωδικό $$1$$, που είναι η δεύτερη προτίμησή του, καθώς η θέση στο πανεπιστήμιο με κωδικό $$2$$ που είναι η πρώτη προτίμησή του έχει ήδη καλυφθεί από τον τρίτο φοιτητή. Τέλος, ο πρώτος φοιτητής επιλέγεται για το πανεπιστήμιο με κωδικό $$3$$ που είναι η τρίτη προτίμησή του, καθώς οι θέσεις στα άλλα πανεπιστήμια έχουν καλυφθεί από τους άλλους δύο φοιτητές.

**2<sup>o</sup>**

| **erasmus.in**      | **erasmus.out** |
| :--- | :--- |
| 3 4 <br> 2 1 1 <br> 59 3 2 3 1 <br> 54 1 2 <br> 81 2 1 3 <br> 22 3 2 1 3 | 2 <br> NONE <br> 1 <br> 1 |

Στο δεύτερο παράδειγμα υπάρχουν πάλι $$3$$ πανεπιστήμια: το πρώτο προσφέρει δύο θέσεις ενώ τα άλλα δύο από μία. Υποβλήθηκαν $$4$$ αιτήσεις. Ο τρίτος και ο πρώτος φοιτητής επιλέγονται αντίστοιχα για τα πανεπιστήμια με κωδικούς $$1$$ και $$2$$, που είναι οι πρώτες προτιμήσεις τους. Ο δεύτερος φοιτητής που έχει ως μοναδική  προτίμηση το πανεπιστήμιο με κωδικό $$2$$ δεν επιλέγεται πουθενά. Τέλος, ο τέταρτος φοιτητής επιλέγεται στη δεύτερη προσφερόμενη θέση του πανεπιστημίου με κωδικό $$1$$, που είναι η δεύτερη προτίμησή του.

## Παρατηρήσεις:

**Μορφοποίηση**: Στην είσοδο αλλά και στην έξοδο, κάθε γραμμή τερματίζει με έναν χαρακτήρα newline.

**Μέγιστος χρόνος εκτέλεσης**: $$1$$ sec.

**Μέγιστη διαθέσιμη μνήμη**: $$64$$ MB.