# SQL tutorial.
## [Dataset](https://www.kaggle.com/datasets/hisanai/elon-musk-tweets-5-years?select=Elon+2021-2022.csv): Elon Musk tweets 2021-2022.

! [Convert](https://www.rebasedata.com/convert-csv-to-sqlite-online) `csv` to `sqlite`.

`Elon 2021-2022` to `data`.

__Columns__:
  ` `
  `Date`
  `Username`
  `Tweet`
  `URL`
  `Media`
  `Likes`
  `Retweets`
  `Quote`
  `Replies`
  `Mentioned Users`
  `Hashtags`
.

## Syntax

#### SELECT
    SELECT DISTINCT * FROM `data` LIMIT 10
    SELECT `Tweet`, `Likes` FROM `data`
    SELECT `Tweet` FROM (SELECT `Tweet`, `Likes` FROM `data`)

#### WHERE
    SELECT * FROM `data` WHERE `Likes` == 0
    SELECT * FROM `data` WHERE `Likes` < 100000
    SELECT * FROM `data` WHERE `Likes` >= 100000

#### AND, OR, NOT
    SELECT * FROM `data` WHERE `Date` > '2021-12-00' AND `Likes` >= 100000
    SELECT * FROM `data` WHERE NOT(`Date` > '2021-12-00' AND `Likes` >= 100000)
    SELECT * FROM `data` WHERE `Date` > '2021-12-00' OR (`Date` > '2021-11-00' AND `Date` < '2021-12-00' AND `Likes` >= 100000)

#### ORDER BY
    SELECT * FROM `data` ORDER BY `Date` DESC

#### MIN, MAX
    SELECT `Date`, `Tweet`, MAX(`Likes`) AS `Most Likes` FROM `data`

#### LIKE
    SELECT * FROM `data` WHERE `Tweet` LIKE '%Elon%'
    SELECT * FROM `data` WHERE `Tweet` LIKE 'No%'
    SELECT * FROM `data` WHERE `Tweet` NOT LIKE '%.'

#### IN, BETWEEN
    SELECT * FROM `data` WHERE ` ` IN (0, 1, 2)
    SELECT * FROM `data` WHERE `Date` BETWEEN '2021-11-00' AND '2021-12-00'

#### CREATE TABLE, UNION ALL
    CREATE TABLE `union` AS (SELECT * FROM `T1`) UNION ALL (SELECT * FROM `T2`)

#### CAST
    SELECT *, CAST(`Date` AS datetime) AS `Datetime` FROM `data`

## Aggregate Functions

#### COUNT
    SELECT *, COUNT(`Tweet`) AS `Tweet Count` FROM `data` GROUP BY `Username`
#### SUM
    SELECT `Username`, SUM(`Likes`) AS `Likes Sum` FROM `data` WHERE `Username` == 'elonmusk' GROUP BY `Username`
#### AVG
    SELECT `Date`, AVG(`Likes`) AS `Likes Avg` FROM `data` WHERE `Date` > '2021-12-00' GROUP BY `Date` HAVING `Likes Avg` > 10000 ORDER BY `Likes Avg` DESC

## String Functions

#### REPLACE
    SELECT *, REPLACE(`Username`, 'elon' || 'musk', 'Elon Musk') AS `User` FROM `data`

#### CHARINDEX, SUBSTRING
    SELECT *, SUBSTRING(`Username`, 1, CHARINDEX(' ', `User`) - 1) AS `Name` FROM `data`

#### SPLIT
    SELECT *, SPLIT(`Tweet`, ' ') AS `Words` FROM `data`

## List Functions

#### EXPLODE
    SELECT *, EXPLODE(`Mentioned Users`) AS `Mentioned` FROM `data`












