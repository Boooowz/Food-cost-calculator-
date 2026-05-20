# 🍽 Cost Manager

> Επαγγελματική κοστολόγηση πιάτων και menu engineering για εστιατόρια. Standalone HTML εφαρμογή με τοπική αποθήκευση και υποστήριξη πολλαπλών εστιατορίων.

[![Live Demo](https://img.shields.io/badge/Live%20Demo-GitHub%20Pages-d4a574?style=flat-square)](https://davidovaselos-9873.github.io/cost-manager/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square)](LICENSE)
[![No Dependencies](https://img.shields.io/badge/dependencies-0-success?style=flat-square)](#)

## 📖 Περιγραφή

Πλήρες εργαλείο κοστολόγησης F&B που υπολογίζει αυτόματα:

- Κόστος πρώτων υλών ανά γραμμάριο / ml / τεμάχιο
- Κόστος πιάτων με sub-recipes (συνταγές μέσα σε συνταγές)
- Food cost percentage και contribution margin ανά πιάτο
- Menu Engineering classification (Stars / Puzzles / Plowhorses / Dogs)

## ✨ Χαρακτηριστικά

### 🏪 Πολλαπλά Εστιατόρια
Διαχείριση 2+ εστιατορίων με ξεχωριστές πρώτες ύλες, συνταγές, πιάτα και πωλήσεις.

### 🥕 Έξυπνη Διαχείριση Πρώτων Υλών
- Καταχώρηση συσκευασίας + τιμή → αυτόματος υπολογισμός κόστους ανά μονάδα
- **Yield %** για ακριβές κόστος μετά το καθάρισμα (π.χ. κρεμμύδι yield 90%)
- Υποστήριξη γραμμαρίων, ml, τεμαχίων

### 🥣 Sub-Recipes (συνταγές μέσα σε συνταγές)
Φτιάχνεις μια σάλτσα μία φορά, την χρησιμοποιείς σε 10 πιάτα. Αλλαγή τιμής σε πρώτη ύλη → αυτόματη ενημέρωση όλων των πιάτων.

### 🍽 Αναλυτική Κοστολόγηση Πιάτων
- Συστατικά + ποσότητες + sub-recipes
- Τιμή πώλησης με υπολογισμό ΦΠΑ
- Food cost %, contribution margin
- **Recipe Cards εκτυπώσιμες** για την κουζίνα

### 📊 Menu Engineering (Boston Matrix)
Αυτόματη ταξινόμηση πιάτων σε 4 κατηγορίες με βάση δημοτικότητα × κερδοφορία:

| Κατηγορία | Περιγραφή | Στρατηγική |
|---|---|---|
| ⭐ **Stars** | Δημοφιλή & Κερδοφόρα | Διατηρούνται, flagship πιάτα |
| ❓ **Puzzles** | Κερδοφόρα, αλλά άγνωστα | Προώθηση από σερβιτόρους |
| ⚙ **Plowhorses** | Δημοφιλή, φτωχό κέρδος | Επανεξέταση κόστους/τιμής |
| ✕ **Dogs** | Μη δημοφιλή, φτωχό κέρδος | Αφαίρεση από τον κατάλογο |

### 📈 Στατιστικά Πωλήσεων
Καταγραφή πωλήσεων ανά περίοδο (μήνας/εβδομάδα) → τροφοδοτεί το menu engineering.

## 🚀 Χρήση

### Online (GitHub Pages)
👉 **[https://davidovaselos-9873.github.io/cost-manager/](https://davidovaselos-9873.github.io/cost-manager/)**

### Τοπικά
1. Κατέβασε το `index.html`
2. Διπλό κλικ → ανοίγει στον browser σου
3. Έτοιμο

## 📚 Παράδειγμα Χρήσης

### 1. Πρώτη Ύλη
```
Ντομάτα κονκασέ
- Συσκευασία: 5000g (5kg)
- Τιμή: 7.50€
- Yield: 100%
→ Κόστος: 0.0015 €/g
```

### 2. Sub-Recipe
```
Σάλτσα Pomodoro (παράγει 2000g)
- 1500g Ντομάτα κονκασέ → 2.25€
- 200g Κρεμμύδι (yield 90%) → 0.44€
- 50ml Ελαιόλαδο → 0.40€
- 30g Σκόρδο → 0.18€
→ Σύνολο: 3.27€ / 2000g = 0.0016 €/g σάλτσας
```

### 3. Πιάτο
```
Σπαγγέτι Pomodoro
- 80g Spaghetti
- 150g Σάλτσα Pomodoro (sub-recipe)
- 30g Παρμεζάνα
→ Κόστος: 0.93€
→ Τιμή πώλησης: 8.50€ (ΦΠΑ 13%)
→ Καθαρή τιμή: 7.52€
→ Food Cost: 12.4% ✓ άριστο
→ Margin: 6.59€
```

## 🧮 Τύποι Υπολογισμού

### Food Cost % Benchmarks
- **≤30%** → Άριστο 🟢
- **30-35%** → Καλό 🟡
- **>35%** → Υψηλό 🔴

### Menu Engineering Thresholds
- **Popularity threshold** = 70% × (1 ÷ πλήθος_πιάτων) — βιομηχανικό πρότυπο
- **Profitability threshold** = μέσος όρος contribution margin

## 🖼 Screenshots

> _Δες την εφαρμογή σε λειτουργία στο [live demo](https://davidovaselos-9873.github.io/cost-manager/)_

## 🛠 Τεχνικά

- **Pure HTML/CSS/JavaScript** — μηδέν εξωτερικές βιβλιοθήκες
- **localStorage** για persistence
- **Single file** — όλα σε ένα `index.html` (~80KB)
- **Offline-first** — δουλεύει χωρίς internet
- **Print-ready** recipe cards με dedicated CSS

## 💾 Backup & Ασφάλεια

Τα δεδομένα αποθηκεύονται **τοπικά στον browser σου** (localStorage):

- **⬇ Backup** → JSON αρχείο με όλα τα εστιατόρια, υλικά, συνταγές, πιάτα, πωλήσεις
- **⬆ Restore** → επαναφορά από JSON

Συνιστάται εβδομαδιαίο backup σε cloud (Google Drive, Dropbox).

## 📄 Άδεια

MIT License — δες [LICENSE](LICENSE)

## 👤 Δημιουργός

**David** — Λογιστής, ιδιοκτήτης εστιατορίων & developer στη Ξάνθη

---

⭐ Αν σε βοήθησε, δώσε ένα star!
