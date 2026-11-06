# Accesso admin con Firebase Authentication

La password e la chiave di scrittura non sono più nel codice: l'admin accede con email e password gestite da Firebase, e le regole del database permettono la scrittura solo a quell'utente.

## Da fare una sola volta, nella console Firebase (progetto `torneo-chievo`)
1. **Authentication → Metodo di accesso**: abilita *Email/password*.
2. **Authentication → Utenti**: aggiungi l'utente admin (email + password robusta) e copia il suo **UID**.
3. **Authentication → Impostazioni → Azioni utente**: disattiva la creazione di nuovi account, se disponibile.
4. **Realtime Database → Regole**: incolla il contenuto di `database.rules.json`, e pubblica.
5. **Cambia la chiave vecchia**: la regola precedente basata su `_wkey` va sostituita dalla nuova (passo 4). Il vecchio valore resta visibile nella cronologia di GitHub, quindi va considerato non più valido.

## Prima del merge
Prova l'accesso con la versione di questo branch prima di unirlo a `main`, perché il sito pubblico viene aggiornato dal merge. Finché le regole nuove non sono pubblicate (passo 4) le modifiche non verranno accettate con questa versione.
