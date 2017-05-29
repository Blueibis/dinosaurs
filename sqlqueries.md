1)
SELECT COUNT(id) FROM dinos;
2)
SELECT name, period
FROM dinos
WHERE period = 'Jurassic';
3)
SELECT SUM(length)
FROM dinos
WHERE period = 'Cretaceous';
4)
SELECT name, species
FROM dinos
WHERE period = 'Cretaceous' OR period = 'Jurassic'
ORDER BY species;
5)
SELECT name, t_order, diet
FROM dinos
WHERE t_order = 'Saurischia' AND diet = 'Herbivorous';
6)
UPDATE dinos
SET name = 'Shortie'
WHERE length in(SELECT MIN(length) FROM dinos);
6-check)
SELECT name, length
FROM dinos
WHERE length in(SELECT MIN(length) FROM dinos);
7)
SELECT name
FROM dinos
ORDER BY name
LIMIT 1;
8)
UPDATE dinos
SET name = 'The Famous Five'
WHERE length in(SELECT length FROM dinos WHERE length > 0 ORDER BY length DESC LIMIT 5);
8-check)
SELECT name, length
FROM dinos
WHERE length > 0
ORDER BY length DESC
LIMIT 6;
