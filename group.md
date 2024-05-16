3. Calcolare la media dei voti di ogni appello d'esame

SELECT COUNT(`exams`.`id` ), AVG(`exam_student`.`vote`) AS `avg_vote`, `date`
FROM `exams`
INNER JOIN `exam_student`
ON `exam_student`.`exam_id` = `exams`.`id`
GROUP BY `date`;


4. Contare quanti corsi di laurea ci sono per ogni dipartimento

SELECT COUNT(`degrees`.`name`) AS `num_degrees`, `departments`.`name` AS `department_name`
FROM `departments`
INNER JOIN `degrees`
ON `departments`.`id` = `degrees`.`department_id`
GROUP BY `departments`.`name`;


2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio


SELECT COUNT(*) AS `teacher_num`, `office_address`
FROM `teachers`
GROUP BY `office_address`;