# JoinOrAssociation
The Fan Trap, in BI Tools and SQL 

Two tables SONG and GENRESONG:

![Tables](/Images/Tables.png)

Load this tables to any BI Tool, in this case I used Power BI.

This is how the model looks inside Power BI:

![Model](/Images/Relation.png)

And this is the result:

![Model](/Images/ResultAssociation.png)

Surprise! It is ten! Notice that if you sum the values (3 + 3 + 4 + 4) = 14,but the report shows 10.  The result of 10 shows us that Power BI is using associations.

If we go to SQL world, we create a view:

```
create or replace view "SONG_GENRE" as
  select 
      T1.SONG,
      T1.DURATION,
      T2.GENRE
  FROM SONGS T1 
  LEFT OUTER JOIN GENRESONG_CSV T2 ON T1.SONG = T2.SONG;
```

If we connect Power BI to the view we get this result:

![Model](/Images/ResultJoin.png)

Contribute by putting the results of how your BI tool will handle this two tables!

(Tables are availabe in Tables folder)

