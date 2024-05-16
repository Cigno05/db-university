1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

SELECT `students`.`id`, `degrees`.`name`
FROM `students`
INNER JOIN `degrees`
ON `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia';


2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di
Neuroscienze

SELECT `degrees`.`name` AS `course_name`, `departments`.`name` AS `department_name`, `degrees`.`level`
FROM `degrees`
INNER JOIN `departments`
ON `departments`.`id` = `degrees`.`department_id`
WHERE `departments`.`name` = 'Dipartimento di Neuroscienze'
AND `degrees`.`level` = 'Magistrale';


3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

SELECT `teachers`.`id` AS `teacher_id`, `courses`.`id` AS `course_id`
FROM `course_teacher`
INNER JOIN `courses`
ON `courses`.`id` = `course_teacher`.`course_id`
INNER JOIN `teachers`
ON `teachers`.`id` = `course_teacher`.`teacher_id`
WHERE `teachers`.`id`= 44;


4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui
sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e
nome
