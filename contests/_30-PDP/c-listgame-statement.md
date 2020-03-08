---
layout: statement
codename: listgame
---

Δίνεται μία λιστα που αποτελείται από $$N$$ φυσικούς αριθμούς. Δύο παίκτες παίζουν το εξής παιχνίδι επαναλαμβάνοντας, πρώτα ο ένας και μετά ο άλλος, την εξής κίνηση: επιλέγουν έναν από τους αριθμούς που βρίσκονται στα άκρα της λίστας (αριστερά ή δεξιά), τον αφαιρούν από τη λίστα και τον προσθέτουν στο σκορ τους. Το παιχνίδι τελειώνει όταν εξαντληθούν οι αριθμοί της λίστας. Κάθε παίκτης προσπαθεί να μεγιστοποιήσει το τελικό του σκορ.

Βρείτε ποιο είναι το μέγιστο σκορ που μπορεί να έχει στο τέλος του παιχνιδιού ο πρώτος παίκτης, αν και αυτός και ο αντίπαλός του παίξουν με βέλτιστο τρόπο.

## Πρόβλημα

Nα αναπτύξετε ένα πρόγραμμα σε μια από τις γλώσσες της IOI (Pascal, C, C++, Java) το οποίο θα διαβάζει τα δεδομένα και θα βρίσκει το μέγιστο δυνατό σκορ του πρώτου παίκτη αν και οι δύο παίξουν με βέλτιστο τρόπο.

## Αρχεία εισόδου

Το αρχείο εισόδου με όνομα **listgame.in** είναι αρχείο κειμένου με ακριβώς δύο γραμμές. Η πρώτη γραμμή του περιέχει έναν ακέραιο αριθμό $$N$$, το πλήθος των αριθμών της λίστας. Η δεύτερη γραμμή περιέχει ακριβώς $$N$$ ακέραιους αριθμούς, χωρισμένους ανά δύο με ένα κενό διάστημα: τους $$N$$ αριθμούς της λίστας.

## Αρχεία εξόδου

Το αρχείο εξόδου με όνομα **listgame.out** είναι αρχείο κειμένου αποτελούμενο από μία γραμμή που θα περιέχει έναν ακέραιο αριθμό: το μέγιστο δυνατό σκορ του πρώτου παίκτη αν και οι δύο παίξουν με βέλτιστο τρόπο.

## Παραδείγματα αρχείων εισόδου - εξόδου

**1<sup>o</sup>**

| **listgame.in**      | **listgame.out** |
| :--- | :--- |
| 10 <br> 6 3 9 2 10 4 9 2 3 7 | 38 |

*Εξήγηση:* Οι δύο παίκτες μπορούν να επιλέξουν να κάνουν τις παρακάτω κινήσεις, κατά σειρά. Οι κινήσεις αυτές είναι βέλτιστες και για τους δύο παίκτες.

| Κίνηση | 1ος παίκτης | 2ος παίκτης | η λίστα μετά την κίνηση |
| :--- | :--- | :--- | :--- |
|0| | | 6 3 9 2 10 4 9 2 3 7|
|1|7| | 7 6 3 9 2 10 4 9 2 3|
|2| |6| 3 9 2 10 4 9 2 3|
|3|3| |3 9 2 10 4 9 2|
|4| |3| 9 2 10 4 9 2|
|5|9| | 2 10 4 9 2|
|6| |2| 2 10 4 9|
|7|9| | 2 10 4|
|8| |4| 2 10|
|9|10| | 2|
|10 | | 2 | |
|σκορ: | 38 | 17 | |

**2<sup>o</sup>**

| **listgame.in**      | **listgame.out** |
| :--- | :--- |
| 5 <br> 10 2 1 4 3 | 14 |

**3<sup>o</sup>**

| **listgame.in**      | **listgame.out** |
| :--- | :--- |
| 6 <br> 4 8 0 1 5 6 | 15 |

## Περιορισμοί:

 * Το άθροισμα όλων των αριθμών της λίστας δε θα ξεπερνά το $$10^9$$.
 * Για περιπτώσεις ελέγχου συνολικής αξίας 25%, θα είναι: $$1 \leq N \leq 20$$
 * Για περιπτώσεις ελέγχου συνολικής αξίας 100%, θα είναι:
   $$1 \leq N \leq 10.000$$


 * **Μορφοποίηση:** Στην είσοδο αλλά και στην έξοδο, κάθε γραμμή τερματίζει με έναν χαρακτήρα newline.
 * **Μέγιστος χρόνος εκτέλεσης:** $$1$$ sec.
 * **Μέγιστη διαθέσιμη μνήμη:** $$64$$ MB.