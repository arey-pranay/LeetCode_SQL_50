#### 1757
- SELECT product_id FROM Products WHERE low_fats='Y' AND recyclable='Y'

#### 584
- SELECT name FROM Customer WHERE (referee_id is null || referee_id!=2)

#### 595
-  SELECT name, population, area FROM World WHERE area >= 3000000 OR population >= 25000000

#### 1148
-  SELECT DISTINCT author_id AS id FROM Views WHERE author_id = viewer_id ORDER BY author_id

#### 1683
-  SELECT tweet_id FROM Tweets WHERE LENGTH(content) > 15
