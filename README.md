# checkTelefono
Programma che ricevuto come parametro un vettore di string, ritorna la prima stringa che assomiglia molto ad un numero di telefono italiano.

## Descrizione del progretto

Realizzazione di un programma in console che permette di riconoscere un numero di telefono italiano. <br>
**Ad esempio:**

- che inizia con +39 (esattamente lungo  13)
- oppure con 0039 (esattamente lungi 14)
- oppure con un 3 (esattamente lungo 10)


## Come funziona?
  
<details>
<summary>Numero che inizia con +39 lungo 13 caratteri </summary>

```c#
        //Questo ciclo si ripete per il numero di stringhe presenti nel vettore input e controlla: 
        //per prima cosa se i primi tre numeri di una stringa sono uguali a +39, in caso controlla anche la lunghezza poi la stampa
        for (int i = 0; i < input.Length; i++)
        {
            string primiTreNumeri = "";
            parola = input[i];
            parola = parola.Replace(" ",""); //rimuovo gli spazi
            while (parola.Length < 10){
                i++;
                parola = input[i];
                parola = parola.Replace(" ","");
            }
           
            for (int j = 0; j < 3; j++) { //inserisce i primi tre numeri di una stringa nella variabile "primiTreNumeri"
             primiTreNumeri += parola[j];
            }
            if (primiTreNumeri == "+39") {
                if (parola.Length == 13){return parola;}
            }
        }
```

Questo pezzo di codice serve a controllare che i primi numeri siano +39 e controllano la lunghezza per verificare che sia un numero di telefono valido
</details>

<details>
<summary>Numero che inizia con 3 lungo 10 caratteri</summary>

```c#
        //questo for guarda se il primo numero è uguale a 3 e se la lunghezza è pari a 10, in caso stampa la stringa
        for (int i = 0; i < input.Length; i++)
        {
            parola = input[i];
            parola = parola.Replace(" ",""); //tolgo gli spazi
            while (parola.Length < 10){
                i++;
                parola = input[i];
                parola = parola.Replace(" ","");
            } 
            if (parola == "") {break;}
            if (parola[0] == '3') {
             if (parola.Length == 10){return parola;}  
            }
        }
```

Questo pezzo di codice controlla se il numero di telefono inizia con 3 e ha 10 numeri, in quel caso il numero è valido
</details>
  
  
<details>
<summary>Numero che inizia con 0039 lungo 14 caratteri</summary>

```c#
       for (int i = 0; i < input.Length; i++){
            string primiQuattroNumeri = "";
            parola = input[i];
            parola = parola.Replace(" ","");
            while (parola.Length < 10){
                i++;
                parola = input[i];
                parola = parola.Replace(" ","");
            }
            for (int j = 0; j < 4; j++){
             primiQuattroNumeri += parola[j];
            }
            if (primiQuattroNumeri == "0039"){
                if (parola.Length == 14){return parola;}     
            }
        }
```

Questo pezzo di codice controlla se i primi quattro numeri sono 0039 e controllano la lunghezza per verificare che sia un numero di telefono valido
</details>
