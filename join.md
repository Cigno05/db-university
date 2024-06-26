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

SELECT `students`.`surname` AS `student_surname`, 
`students`.`name` AS `student_name`, 
`degrees`.`name` AS `degree_name`,
`departments`.`name` AS `department_name`
FROM `students`
INNER JOIN `degrees`
ON `students`.`degree_id` = `degrees`.`id`
INNER JOIN `departments`
ON `departments`.`id` = `degrees`.`department_id`
ORDER BY `students`.`surname` ASC;


5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

SELECT `degrees`.`name` AS `degree_name`,
`courses`.`name` AS `course_name`,
`teachers`.`name` AS `teacher_name`,
`teachers`.`surname` AS `teacher_surname`
FROM `courses`
INNER JOIN `degrees`
ON `courses`.`degree_id` = `degrees`.`id`
INNER JOIN `course_teacher`
ON `courses`.`id` = `course_teacher`.`course_id`
INNER JOIN `teachers`
ON `teachers`.`id` = `course_teacher`. `teacher_id`
ORDER BY `degrees`.`name` ASC;


6. Selezionare tutti i docenti che insegnano nel Dipartimento di
Matematica (54)


SELECT DISTINCT `teachers`.`name` AS `teacher_name`,
`teachers`.`surname` AS `teacher_surname`,
`departments`.`name` AS `department_name`
FROM `teachers`
INNER JOIN `course_teacher`
ON `teachers`.`id` = `course_teacher`.`teacher_id`
INNER JOIN `courses`
ON `courses`.`id` = `course_teacher`.`course_id`
INNER JOIN `degrees`
ON `degrees`.`id` = `courses`.`degree_id`
INNER JOIN `departments`
ON `departments`.`id` = `degrees`.`department_id`
WHERE `departments`.`name` = 'Dipartimento di Matematica'  
ORDER BY `teacher_surname` ASC;
