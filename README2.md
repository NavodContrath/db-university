# Esercizio db_university con sql.

1. Selezionare tutti gli studenti nati nel 1990 (160)**160**✅
(SELECT `name`
FROM `students`
WHERE YEAR(`date_of_birth`)='1990')

2. Selezionare tutti i corsi che valgono più di 10 crediti (479)**479**✅
(SELECT `name`
FROM `courses`
WHERE `cfu`>'10')

3. Selezionare tutti gli studenti che hanno più di 30 anni **1000**✅
(SELECT `name`,`date_of_birth`
FROM `students`
WHERE `date_of_birth`<'1995-04-10')
(SELECT *
FROM `students`
WHERE TIMESTAMPDIFF(YEAR, date_of_birth, CURDATE())	>30)

4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)**286**✅
(SELECT `name`,`period`,`year`
FROM `courses`
WHERE `period`='I semestre'
AND `year` = '1')

5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)**21**✅
(SELECT `course_id`,`date`,`hour`
FROM `exams`
WHERE `date`='2020-06-20'
AND `hour` >= '14:00:00')

6. Selezionare tutti i corsi di laurea magistrale (38)**38**✅
(SELECT `name`,`level`
FROM `degrees`
WHERE `level`='magistrale')

7. Da quanti dipartimenti è composta l'università? (12)**12**✅
(SELECT `name`
FROM `departments`)

8. Quanti sono gli insegnanti che non hanno un numero di telefono? (50)**50**✅
(SELECT `name`,`phone`
FROM `teachers`
WHERE `phone` IS NULL)