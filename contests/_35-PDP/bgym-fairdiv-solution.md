---
layout: solution
codename: fairdiv
---

## Επεξήγηση εκφώνησης

Μας δίνονται $$N$$ μη-αρνητικοί ακέραιοι $$A_0, \ldots, A_{N-1}$$. Θέλουμε να τους χωρίσουμε σε τρία μέρη $$S_A = A_0 + \ldots + A_{i_A}$$, $$S_B = A_{i_A + 1} + \ldots + A_{i_B}$$ και $$S_C = A_{i_B + 1} + \ldots + A_{N - 1}$$ έτσι ώστε $$S_A \geq S_B \geq S_C$$ και το $$S_C$$ είναι όσο πιο μεγάλο γίνεται. Από όλες τις λύσεις που μεγιστοποιούν το $$S_C$$, διαλέγουμε αυτήν που μεγιστοποιεί το $$S_B$$.

## Brute force λύση

Υπάρχουν συνολικά $$N-1$$ θέσεις για το $$i_A$$ και το πολύ $$N-2$$ θέσεις για το $$i_B$$. Το $$i_A$$ και το $$i_B$$ καθορίζουν τα $$S_A$$, $$S_B$$ και $$S_C$$. Μπορούμε, επομένως να δοκιμάσουμε όλες τις πιθανές μοιρασιές και να υπολογίσουμε τα $$S_A, S_B, S_C$$ (διατρέχοντας μία φορά τον πίνακα) κρατώντας την καλύτερη από αυτές.

{% include code.md solution_name='fairdiv_brute_force.cc' %}

Υπάρχουν συνολικά $$(N-1) \cdot (N-2) = \mathcal{O}(N^2)$$ δυνατές μοιρασιές και η συνάρτηση $$\texttt{compute_sum}$$ χρειάζεται $$\mathcal{O}(N)$$ χρόνο. Επομένως, ο αλγόριθμος χρειάζεται συνολικά $$\mathcal{O}(N^3)$$ χρόνο για να τρέξει.

## Λύση με prefix sums

Μπορούμε να επιταχύνουμε τον παραπάνω αλγόριθμο, επιταχύνοντας τη συνάρτηση $$\texttt{compute_sum}$$. Πιο συγκεκριμένα μπορούμε να υπολογίσουμε τα prefix sums (προθεματικά αθροίσματα) $$S[\cdot]$$, όπου $$S[i+1] = A_0 + \ldots + A_i$$ και $$S[0] = 0$$.

Συνεπώς το άθροισμα $$A_i + \ldots + A_j$$ για οποιαδήποτε $$i$$ και $$j$$ (με $$j \geq i$$) δίνεται από τον τύπο $$S[j+1] - S[i]$$ (*μπορείτε να δείτε γιατί;*[^exigisi]).

[^exigisi]: Επειδή $$S[j+1] - S[i] = (A_0 + \ldots + A_j) - (A_0 + \ldots + A_{i-1}) = A_i + \ldots + A_j$$.

Το μόνο που χρειάζεται να αλλάξουμε είναι η υλοποίηση αυτής της συνάρτησης 
{% include code.md solution_name='fairdiv_prefix_sums.cc' start=10 end=14 %}
και να προϋπολογίσουμε τις τιμές του $$S[\cdot]$$
{% include code.md solution_name='fairdiv_prefix_sums.cc' start=21 end=25 %}

Ο αλγόριθμος χρειάζεται $$\mathcal{O}(1)$$ χρόνο για κάθε μοιρασιά και επομένως συνολικά $$\mathcal{O}(N^2)$$ χρόνο. Μπορείτε να βρείτε ολόκληρο τον κώδικα [εδώ]({% include link_to_source.md solution_name='fairdiv_prefix_sums.cc' %}).

## Λύση με δυαδική αναζήτηση

Ξεκινάμε με την εξής παρατήρηση:

**Παρατήρηση:** Έστω ότι έχουμε αποφασίσει ότι θα δώσουμε τα στοιχεία $$A_0, \ldots, A_{i_A}$$ στον $$A$$. Τότε, αυξάνοντας το $$i_B$$ το άθροισμα $$S_B$$ αυξάνει (ή μένει το ίδιο). Επομένως, θέλουμε να βρούμε το μικρότερο $$i_B$$ ώστε $$S_B \geq S_C$$, καθώς αυτό μεγιστοποιεί το $$S_C$$.

Επειδή έχουμε ότι το $$S_B$$ αυξάνει μονότονα, μπορούμε να χρησιμοποιήσουμε δυαδική αναζήτηση για να βρούμε το βέλτιστο $$i_B$$ για κάθε $$i_A$$, δηλαδή το μικρότερο $$i_B > i_A$$ τέτοιο ώστε $$A_{i_A+1} + \ldots + A_{i_B} > A_{i_B + 1} + \ldots + A_{N-1}$$. Ο παρακάτω κώδικας υλοποιεί το μέρος της δυαδικής αναζήτητης.

{% include code.md solution_name='fairdiv_bsearch.cc' start=29 end=42 %}

Μπορείτε να βρείτε ολόκληρο τον κώδικα [εδώ]({% include link_to_source.md solution_name='fairdiv_bsearch.cc' %}). Κάθε δυαδική αναζήτηση θέλει $$\mathcal{O}(\log N)$$ χρόνο, συνεπώς ο αλγόριθμος χρειάζεται συνολικά $$\mathcal{O}(N \log N)$$ χρόνο.

## Λύση με δύο δείκτες

Για να λύσουμε το πρόβλημα σε $$\mathcal{O}(N)$$ χρόνο, κάνουμε την εξής παρατήρηση:

**Παρατήρηση:** Έστω ότι έχουμε αποφασίσει ότι θα δώσουμε τα στοιχεία $$A_0, \ldots, A_{i_A}$$ στον $$A$$ και η βέλτιστη μοιρασιά για τα υπόλοιπα στοιχεία χρησιμοποιούν το $$i_B$$. Τότε, η βέλτιστη λύση για το $$i_A' = i_A - 1$$ θα έχει $$i_B' \leq i_B$$, δηλαδή ο δείκτης μετακινείτε προς τα αριστερά (ή μένει στο ίδιο σημείο).

Για παράδειγμα, αλλάζοντας το $$i_A = 2$$ σε $$i_A' = 1$$, οδηγεί στο βέλτιστο $$i_B$$ από $$8$$ σε $$i_B' = 4$$.

![Παράδειγμα για τους δύο δείκτες](/assets/35-pdp-bgym-fairdiv-two-pointers-example.svg){:width="50%"}

Ο λόγος που το $$i_B$$ μετακινείται προς τα αριστερά είναι ότι το $$S_B$$ μεγαλώνει, επομένως δίνεται η δυνατότητα στο $$S_C$$ να μεγαλώσει.

Συνεπώς, ξεκινώντας από $$i_A = N - 1$$ και $$i_B = N$$, μετακινούμε το $$i_A$$ προς τα αριστερά κατά μία θέση, και μετά το $$i_B$$ όσο χρειάζεται προς τα αριστερά. Ως τελική απάντηση δίνουμε το βέλτιστο από όλα τα $$i_A$$.

{% include code.md solution_name='fairdiv_two_pointers.cc' start=28 end=42 %}

Επειδή το $$i_B$$ μπορεί να μετακινηθεί το πολύ $$N$$ θέσεις, η εσωτερική επανάληψη μπορεί να εκτελεστεί το πολύ $$N$$ φορές καθ'όλη την εκτέλεση του αλγορίθμου. Έτσι, παρότι με μια πρόχειρη ματιά θα νομίζαμε ότι ο αλγόριθμος τρέχει σε $$\mathcal{O}(N^2)$$ χρόνο, στην πραγματικότητα τρέχει μόνο σε $$\mathcal{O}(N)$$ χρόνο. Για παρόμοια παραδείγματα, μπορείτε να ψάξετε "amortized analysis".
