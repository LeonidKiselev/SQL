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

__Queries__:

1. SELECT
    SELECT * FROM `data` LIMIT 10
    SELECT DISTINCT `Username` FROM `data`

2. WHERE
    SELECT `Tweet`, `Likes` FROM `data` WHERE `Likes` == 0
    SELECT `Tweet`, `Likes` FROM `data` WHERE `Likes` < 100000
    SELECT `Tweet`, `Likes` FROM `data` WHERE `Likes` >= 100000

3. AND, OR, NOT
    
    
