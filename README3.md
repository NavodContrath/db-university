# JOIN
1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia **68**
(
SELECT `students`.`name` as `student_name`, `students`.`surname` as `student_surname`,`students`.`registration_number`,`degrees`.`name` as degree_`name`,`degrees`.`level`
FROM `students`
JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name` LIKE '%Laurea in Economia'
)
2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze **1**
(
SELECT `degrees`.`name` as `degree_name`,`degrees`.`level`,`departments`.`name`,`departments`.`id`
FROM `degrees`
JOIN `departments` ON `degrees`.`department_id` =`departments`.`id`
WHERE `departments`.`name` = 'Dipartimento di Neuroscienze'
AND `degrees`.`level` = 'magistrale'
)
3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)**11**
(
SELECT `teachers`.`id`,`teachers`.`name` as `teacher_name`,`teachers`.`surname` as `teacher_surname`,`teachers`.`office_number`,`courses`.`name` as `course_name`,`courses`.`period`,`courses`.`year`
FROM `teachers`
JOIN `course_teacher` ON `course_teacher`.`teacher_id` = `teachers`.`id`
JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id`
WHERE `teachers`.`name` = 'Fulvio'
AND `teachers`.`surname`='Amato'
)

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome
5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)
7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.
# GROUP BY
1. Contare quanti iscritti ci sono stati ogni anno
2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio
3. Calcolare la media dei voti di ogni appello d'esame
4. Contare quanti corsi di laurea ci sono per ogni dipartimento

# RIPASSINO SELECT (extra bonus opzionale per il weekend):
1. Selezionare tutti gli insegnanti
2. Selezionare tutti i referenti per ogni dipartimento
3. Selezionare tutti gli studenti il cui nome inizia per "E" (373)
4. Selezionare tutti gli studenti che si sono iscritti nel 2021 (734)
5. Selezionare tutti i corsi che non hanno un sito web (676)
6. Selezionare tutti gli insegnanti che hanno un numero di telefono (50)
7. Selezionare tutti gli appelli d'esame dei mesi di giugno e luglio 2020 (2634)
8. Qual è il numero totale degli studenti iscritti? (5000)