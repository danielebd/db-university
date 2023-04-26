1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

SELECT
    `students`.*,
    `degrees`.`name`
FROM
    `students`
JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
WHERE
    `degrees`.`name` = 'Corso di Laurea in Economia';

2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

SELECT
    `degrees`.*,
    `departments`.`name`
FROM
    `degrees`
JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
WHERE
    `departments`.`name` = 'Dipartimento di Neuroscienze';


3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

SELECT
    `courses`.*, `teachers`.`name`
FROM
    `courses`
JOIN `course_teacher` ON `courses`.`id` = `course_teacher`.`course_id`
JOIN `teachers` ON `course_teacher`.`teacher_id` = `teachers`.`id`
WHERE
    `teachers`.`id`= 44;

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il
relativo dipartimento, in ordine alfabetico per cognome e nome

SELECT
    `students`.`surname`,
    `students`.`name`,
    `students`.`id`,
    `degrees`.*,
    `departments`.`name`
FROM
    `students`
JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
ORDER BY
    `students`.`surname` ASC;


5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti


6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)


7. BONUS: Selezionare per ogni studente quanti tentativi d’esame ha sostenuto per
superare ciascuno dei suoi esami