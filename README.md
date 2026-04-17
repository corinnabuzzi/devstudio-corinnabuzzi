# DevStudio — Sito Vetrina

Progetto realizzato come esame finale del corso Git & GitHub.

## Struttura del progetto

- `index.html` — Homepage
- `servizi.html` — Pagina servizi
- `team.html` — Pagina team
- `contatti.html` — Pagina contatti
- `chi-siamo.html` — Pagina chi siamo
- `404.html` — Pagina di errore
- `style.css` — Stili principali
- `typography.css` — Stili tipografici
- `.gitignore` — File ignorati da Git

## Informazioni dal repository

1. Numero totale di commit su main (edit: master): 24
2. Hash breve del primo commit in assoluto: 9cf03e9 
3. Numero di Pull Request aperte durante il progetto: 4

## Commenti commit



11. **55a5320** feat: aggiunta pagina 404

12. **c11f441** Merge pull request #4 from corinnabuzzi/feature/404

13. **bd10ece** feat: aggiornamento colore header variante A

14. **fc700c4** feat: aggiornamento colore header variante B

15. **27fd50a** fix: risolto conflitto colore header, scelta variante A

16. **045c083** fix: aggiornamento titolo pagina servizi

17. **e81f27a** feat: aggiunto file tipografia

18. **01cba62** feat:stili creativi homepage

19. **67160a8** Revert "feat:stili creativi homepage"

20. **460aa49** feat: struttura pagina chi siamo

21. **672a285** feat:stili pagina chi siamo

22. **280ee67** feat: aggiunto link chi siamo alla navigazione

23. **0c2cbbf** feat: aggiunta sezione chi siamo

24. **b792c76** (HEAD -> master, origin/master, origin/HEAD) Merge branch 'feature/ch
i-siamo'

### Inizializzazione 
Creazione directory locale e inizializzazione locale della repository git:
```bash
mkdir devstudio-corinnabuzzi
git init
git remote add origin [link della repo]
```

Configurazione dei file da ignorare
```bash
touch .gitignore
nano .gitignore
```

Creazione e scrittura primi file del sito, `index.html` e `styles.css`.

Commit:
**9cf03e9** - chore: aggiunto .gitignore
**7e0298a** - feat:aggiunta homepage
**2d6ecef** - feat:aggiunto foglio di stile

Note:
commit "chore": gestione del progetto;
commit "feat": aggiunta feature al prodotto.

commit diretti su `master`, unica branch esistente.

### Feature branches

#### Servizi
Prima nuova branch: `feature/servizi` 
```
git checkout -b feature/servizi
```
per creare la branch e spostarcisi in un singolo comando.


Creazione di `servizi.html`, aggiornamento stili css, push della branch sul remote e collegamento upstream:
```bash
git push -u origin feature/servizi`
```

Apertura pull request da github e merge commit per unire storia di `main` e `feature/servizi`.

**e0876e3** Merge pull request #1 from corinnabuzzi/feature/servizi
**b05101f** feat: aggiunta pagina servizi

#### Team
Creazione branch `feature/team`, edit file team.html da nuova branch, ma nessuna commit. 
modifiche salvate temporaneamente con `stash`:
```bash
git stash -u
```

Lo stash consente di sospendere temporaneamente modifiche non completate senza dover creare commit parziali, permettendo di cambiare contesto di lavoro in modo sicuro.
Spostamento su branch principale (`git switch master`),modifica contenuto di homepage, commit della modifica correttiva:
```bash
git add index.html
git commit -m "fix: aggiornamento testi homepage"
```
commit "fix": no aggiunte, solo correzioni.

Ritorno a branch `feature/team`, e recupero modifiche salvate con
```bash
git stash pop
```
Ancora merge della feature/team branch tramite github PR.

La branch viene pushata con PR da github.

**472a7b5** fix: aggiornamento testi homepage
**93451a3** Merge pull request #2 from corinnabuzzi/feature/team

### Amend
Creazione della branch `feature/contatti` e sviluppo della nuova pagina `contatti.html`.

primo commit incompleto (manca lo stylesheet aggiornato!), quindi la feature non è completa: la commit è da correggere. 

dopo aver aggiunto le regole mancanti in `style.css`, invece di creare un nuovo commit si corregge quello precedente con:

```bash
git add style.css
git commit --amend
```
il commit precedente viene riscritto, modifiche unificate, e poi commit aggiornato. 

poi `push`, pull request, e merge con master.

**a47c0e4** feat: aggiunta pagina contatti con stili
**77ea189** Merge pull request #3 from corinnabuzzi/feature/contatti

### Reset
Creazione del file 404.html direttamente sulla branch principale (master): incoerente con workflow fino ad ora; doveva essere creato da branch dedicata.
```bash
git reset --soft HEAD~1
```
il commit viene rimosso dalla cronologia, ma le modifiche restano nello staging e non vengono perse.

Creazione branch corretta,
```bash
git checkout -b feature/404
```
le modifiche già presenti nello staging vengono committate, e la branch viene pushata e integrata tramite Pull Request


Nuovo file html da branch principale `master`, ma doveva essere da branch specifica.
`git reset --soft HEAD~1` per annullare il commit.
creazione branch dedicata (`feature/404`), stage e commit, push e PR da github.

### Cronologia



`