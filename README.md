SELECT SU UNICA TABELLA
1. Seleziona tutti gli ospiti che sono stati identificati con la carta di identità
>SELECT * FROM ospiti where document_type ='CI'
2. Seleziona tutti gli ospiti che sono nati dopo il 1988
> SELECT * FROM ospiti WHERE date_of_birth >= '1989/01/01'
3. Seleziona tutti gli ospiti il cui nome inizia con la D
> SELECT * FROM ospiti WHERE name LIKE 'D%'
4. Calcola il totale incassato degli ordini accepted (res : 4164.00)
> SELECT SUM(price)
FROM pagamenti
WHERE status='accepted'
5. Qual è il prezzo massimo pagato? (res : 869.00)
> SELECT TOP 1 price
FROM pagamenti
WHERE status='accepted'
ORDER BY price DESC
6. Quanti posti letto ha l’hotel in totale?
> SELECT COUNT(beds) FROM stanze

GROUP BY

7. Somma i prezzi dei pagamenti raggruppandoli per status
> SELECT status AS Stato_Transazione, SUM(price) AS Somma_Complessiva
FROM pagamenti
GROUP BY status

8. Conta quante volte è stata prenotata ogni stanza
> SELECT stanza_id AS Numero_Stanza, COUNT(stanza_id) AS Prenotazioni_Totali
FROM prenotazioni
GROUP BY stanza_id

JOIN

9. Stampare tutti gli ospiti per ogni prenotazione
> SELECT prenotazioni.id AS ID_Prenotazione, ospiti.name + ' ' + ospiti.lastname AS Nominativo, prenotazioni.stanza_id AS Numero_Di_Stanza
FROM ospiti 
INNER JOIN prenotazioni_has_ospiti ON ospiti.id = prenotazioni_has_ospiti.ospite_id
INNER JOIN prenotazioni ON prenotazioni_has_ospiti.prenotazione_id = prenotazioni.id
ORDER BY prenotazioni.id
10. Fai la somma di tutti i prezzi delle prenotazioni per le stanze del primo piano
> SELECT SUM(price) AS 'Guadagno Totale dalle stanze al Primo Piano', status AS Esito
FROM stanze 
INNER JOIN prenotazioni ON prenotazioni.stanza_id = stanze.id
INNER JOIN pagamenti ON pagamenti.prenotazione_id = prenotazioni.id
WHERE (stanze.floor=1) AND (pagamenti.status='accepted') OR (pagamenti.status='pending')
GROUP BY status
11. Le stanze sono state tutte prenotate almeno una volta? (Visualizzare le stanze
non ancora prenotate) - BONUS
> SELECT
