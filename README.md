# Tyrell_Test_B
Written explanation of SQL improvement logic test

•	Extra fields increase the grain of the data returned resulting in more time taken to process the data  
•	Suggestion is to only select necessary field or use subquery instead of left join  
•	Most of the cases, left join is slow because it will compare both tables completely. with sub query, the nested query will give faster result as it will contain few conditions, then upper query will run which will also be fast as it will have to compare only those results that subquery gives  
•	Ensure indexes are available on the fields that are in the WHERE statements and ON conditions. Primary keys are indexed by default, but indexes can also be created manually. Otherwise MySQL will go through every row in the table. Indexes speed up the performance of the query  
•	The ON clause should only be used to show how the tables are related, it should not be used for “filtering”, which should be moved to the WHERE clause  
•	Wildcard usage brings major performance limitation. The predicate LIKE '%キャビンアテンダント%' causes full table scan. Suggestion is to use exact matching instead of LIKE operator in OR clause.  
•	If the values are constant, IN sorts the list and then uses a binary search. OR evaluates them one by one in no particular order. So IN is faster. IN operator can be used rather than OR operator for query optimization. 
