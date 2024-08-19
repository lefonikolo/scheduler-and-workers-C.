# scheduler-and-workers

# Περιγραφή Προγράμματος

Αυτό το πρόγραμμα σε γλώσσα C χρησιμοποιεί πολυεπεξεργασία (multiprocessing) και σηματοδότηση (signaling) για να εκτελεί μια σειρά από μαθηματικές πράξεις σε παράλληλες διεργασίες (child processes). Συγκεκριμένα:

1. Δημιουργία Pipes: Το πρόγραμμα δημιουργεί έξι ζεύγη pipes για την επικοινωνία μεταξύ της κύριας διεργασίας (parent process) και των έξι παράλληλων διεργασιών.

2. Υπολογισμός Μαθηματικών Εκφράσεων: Κάθε child process αναλαμβάνει την εκτέλεση μιας μαθηματικής πράξης (προσθήκη, αφαίρεση, πολλαπλασιασμός, διαίρεση). Οι μαθηματικές πράξεις εκτελούνται με βάση τα αποτελέσματα των προηγούμενων πράξεων σε μια αλληλουχία που καταλήγει σε ένα τελικό αποτέλεσμα.

3. Χρήση Signals: Κάθε child process στέλνει ένα signal στην κύρια διεργασία μετά την ολοκλήρωση της πράξης του, ειδοποιώντας την να προχωρήσει στην επόμενη πράξη. Οι signal handlers είναι υπεύθυνοι για την επεξεργασία των εισερχόμενων δεδομένων από τα pipes και την εκτέλεση των αντίστοιχων πράξεων.

4. Συγχρονισμός Διεργασιών: Ο συγχρονισμός μεταξύ των child processes επιτυγχάνεται με τη χρήση signals και τη σειρά εκτέλεσης των πράξεων. Το πρόγραμμα περιμένει την ολοκλήρωση των child processes πριν εκτυπώσει το τελικό αποτέλεσμα.

5. Τελικό Αποτέλεσμα: Το πρόγραμμα ολοκληρώνεται με την εκτύπωση του τελικού αποτελέσματος που προκύπτει από την αλληλουχία των μαθηματικών πράξεων.
   
Αυτό το πρόγραμμα είναι ένα παράδειγμα χρήσης βασικών τεχνικών IPC (Inter-Process Communication) και signaling για την παράλληλη επεξεργασία δεδομένων σε Unix.
