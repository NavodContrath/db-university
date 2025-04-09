# Consegna
Modellizzare la struttura di un database per memorizzare tutti i dati riguardanti una università:

sono presenti diversi **Dipartimenti** (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
ogni **Dipartimento** offre più **Corsi** di Laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
ogni **Corso** di Laurea prevede diversi **Corsi** (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
ogni **Corso** può essere tenuto da diversi **Insegnanti**;
ogni **Corso** prevede più appelli d'**Esame**;
ogni **Studente** è iscritto ad un solo **Corso** di Laurea;
ogni **Studente** può iscriversi a più appelli di **Esame**;
per ogni appello d'**Esame** a cui lo **Studente** ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente. Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella.

# Universyty_DB

## Table: `departments`

**columns**:

- id 
- name

## Table: `degreeCourses`

**columns**:
- id
- name
- depatmment_id

## Table: `courses`

**columns**:

- id
- name

## Table: `course_degreeCourse`

**columns**:

- course_id
- degreeCourse_id

## Table: `teachers`

**columns**:

- id
- name
- lastname
- email

## Table: `course_teacher`

**columns**:

- course_id
- teacher_id

## Table: `exams`

**columns**:

- id
- course_id
- date
- hall

## Table: `students`

**columns**:

- id
- name
- lastname
- email

## Table: `examsResults`

**columns**:

- student_id
- exam_id
- score


