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
WHERE `teachers`.`id` = '44'
)

**I BACK TIC😭**

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome
(
SELECT students.id,students.surname as student_surname, students.name as student_name,students.registration_number,degrees.name as degree_name,degrees.level,departments.name as department_name,departments.head_of_department
FROM students
JOIN degrees ON degrees.id = students.degree_id
JOIN departments ON departments.id = degrees.department_id
ORDER BY students.surname, students.name ASC

)
5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
(
SELECT degrees.name as degree_name,degrees.level,courses.name as course_name,courses.period,courses.year,courses.cfu,course_teacher.teacher_id,teachers.name as teacher_name, teachers.surname as teacher_name,teachers.office_number
FROM degrees
JOIN courses ON courses.degree_id = degrees.id
JOIN course_teacher ON course_teacher.course_id = courses.id
JOIN teachers ON course_teacher.teacher_id = teachers.id
)
6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)
(
SELECT DISTINCT teachers.* , departments.*
FROM teachers
JOIN course_teacher ON course_teacher.teacher_id = teachers.id
JOIN courses ON course_teacher.course_id = courses.id
JOIN degrees ON courses.degree_id = degrees.id
JOIN departments ON degrees.department_id = departments.id
WHERE departments.name = 'Dipartimento di Matematica'
)

7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.
(

)
# GROUP BY
1. Contare quanti iscritti ci sono stati ogni anno
(
SELECT YEAR(students.enrolment_date) AS year,COUNT(students.id) AS total_students
FROM students
GROUP BY YEAR(students.enrolment_date)
ORDER BY year ASC;
)
2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio
(
SELECT  COUNT(teachers.id) as teachers_number,teachers.office_address
FROM teachers
GROUP BY teachers.office_address
)
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