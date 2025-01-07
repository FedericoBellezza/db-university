# Query con SELECT

1. Selezionare tutti gli studenti nati nel 1990 (160)

```
    SELECT *
    FROM `university`.`students`
    WHERE YEAR (`date_of_birth`) = 1990
```

2. Selezionare tutti i corsi che valgono più di 10 crediti (479)

```
    SELECT *
    FROM university.courses
    WHERE `cfu` > 10
```

3. Selezionare tutti gli studenti che hanno più di 30 anni

```
    SELECT *
    FROM `university`.`students`
    WHERE `date_of_birth` < "1995-01-07"
```

4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)

```
    SELECT *
    FROM university.courses
    WHERE `period` = "I semestre" AND `year` = 1
```

5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)

```
    SELECT *
    FROM university.exams
    WHERE `date` = "2020-06-20" AND `hour` > "14:00:00"
```

6. Selezionare tutti i corsi di laurea magistrale (38)

```
    SELECT *
    FROM university.degrees
    WHERE `level` = "magistrale"
```

7. Da quanti dipartimenti è composta l'università? (12)

```
    SELECT COUNT(*) FROM `university`.`departments`
```

8. Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

```
    SELECT COUNT(*)
    FROM university.teachers
    WHERE `phone` IS NULL
```

9. Inserire nella tabella degli studenti un nuovo record con i propri dati (per il campo degree_id, inserire un valore casuale)

```
    INSERT INTO `university`.`students` (degree_id, name, surname, date_of_birth, email, registration_number, fiscal_code)
    VALUES (55, "Federico", "Bellezza", "2001-04-21", "federico@gmail.com", "60125", "BLLFRC01D32L217B")
```

10. Cambiare il numero dell’ufficio del professor Pietro Rizzo in 126

```
    UPDATE `university`.`teachers`
    SET `phone` = "126"
    WHERE `name` = "Pietro" AND `surname` = "Rizzo"
```

11. Eliminare dalla tabella studenti il record creato precedentemente al punto 9

```
    DELETE FROM `university`.`students`
    WHERE `name` = "Federico" AND `surname` = "Bellezza" and `date_of_birth` = "2001-04-21"
```