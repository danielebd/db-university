1. Contare quanti iscritti ci sono stati ogni anno

SELECT
    YEAR(`enrolment_date`) AS `ANNO REGISTRAZIONE`,
    COUNT(`id`) AS `STUDENTE`
FROM
    `students`
GROUP BY
    YEAR(`enrolment_date`);

2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

SELECT
    `office_address` AS `uffico`,
    COUNT(`id`) AS `insegnati`
FROM
    `teachers`
GROUP BY
    `office_address`;


3. Calcolare la media dei voti di ogni appello d'esame

SELECT
    `exam_id` AS `esame`,
    AVG(`vote`) AS `media`
FROM
    `exam_student`
GROUP BY
    `exam_id`;


4. Contare quanti corsi di laurea ci sono per ogni dipartimento

SELECT
    `departments`.`name` AS `dipartimento`,
    COUNT(`degrees`.`id`) AS `corsi`
FROM
    `departments`
JOIN `degrees` ON `departments`.`id` = `degrees`.`department_id`
GROUP BY
    `departments`.`name`;