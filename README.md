# UniversityRankingSystem
 
SELECT
    u.university_name,
    r.ranking_system,
    r.year,
    rc.criteria_name,
    ury.score
FROM
    university_ranking_year ury
JOIN
    university u ON ury.university_id = u.university_id
JOIN
    ranking_criteria rc ON ury.criteria_id = rc.criteria_id
JOIN
    ranking_system r ON ury.ranking_system_id = r.ranking_system_id
WHERE
    r.year BETWEEN [start_year] AND [end_year]
ORDER BY
    u.university_name, r.ranking_system, r.year;
