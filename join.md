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