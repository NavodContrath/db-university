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

- id BIGINT - primary key - auto_increment - NOT NULL
- name VARCHAR(100) - NOT NULL

## Table: `degreeCourses`

**columns**:
- id BIGINT - primary key - auto_increment - NOT NULL
- name VARCHAR(100) - NOT NULL
- departmment_id BIGINT - foreign key

## Table: `courses`

**columns**:

- id BIGINT - primary key - auto_increment - NOT NULL
- name VARCHAR(100) - NOT NULL

## Table: `teachers`

**columns**:

- id BIGINT - primary key - auto_increment - NOT NULL
- name VARCHAR(100) - NOT NULL
- lastname VARCHAR(100) - NOT NULL
- email VARCHAR(100) - NULL - UNIQUE

## Table: `exams`

**columns**:

- id BIGINT - primary key - auto_increment - NOT NULL
- course_id BIGINT - foreign key
- date DATETIME - NOT NULL
- hall VARCHAR(50) - NOT NULL

## Table: `students`

**columns**:

- id BIGINT - primary key - auto_increment - NOT NULL
- name VARCHAR(100) - NOT NULL
- lastname VARCHAR(100) - NOT NULL
- email VARCHAR(100) - NULL - UNIQUE

## Table: `exam_student`

**columns**:

- student_id BIGINT - foreign key
- exam_id BIGINT - foreign key
- score TINYINT - NOT NULL


