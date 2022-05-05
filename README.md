SELECT SU UNICA TABELLA
1. Seleziona tutti gli ospiti che sono stati identificati con la carta di identità
>SELECT * FROM ospiti where document_type ='CI'
2. Seleziona tutti gli ospiti che sono nati dopo il 1988
> SELECT * FROM ospiti WHERE date_of_birth >= '1989/01/01'
3. Seleziona tutti gli ospiti il cui nome inizia con la D
> SELECT * FROM ospiti WHERE name LIKE 'D%'
4. Calcola il totale incassato degli ordini accepted (res : 4164.00)
> SELECT 
5. Qual è il prezzo massimo pagato? (res : 869.00)
> SELECT
6. Quanti posti letto ha l’hotel in totale?
> SELECT
GROUP BY
7. Somma i prezzi dei pagamenti raggruppandoli per status
> SELECT
8. Conta quante volte è stata prenotata ogni stanza
> SELECT
JOIN
9. Stampare tutti gli ospiti per ogni prenotazione
> SELECT
10. Fai la somma di tutti i prezzi delle prenotazioni per le stanze del primo piano
> SELECT
11. Le stanze sono state tutte prenotate almeno una volta? (Visualizzare le stanze
non ancora prenotate) - BONUS
> SELECT
