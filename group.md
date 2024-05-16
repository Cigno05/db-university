3. Calcolare la media dei voti di ogni appello d'esame

SELECT COUNT(`exams`.`id` ), AVG(`exam_student`.`vote`) AS `avg_vote`, `date`
FROM `exams`
INNER JOIN `exam_student`
ON `exam_student`.`exam_id` = `exams`.`id`
GROUP BY `date`;


