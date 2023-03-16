# mongoDB_assignment

* By simply giving the command ‘use dbname’ we can create the database in Mongodb.<br>
* After that we need to make a collection which is analogous to tables in SQL.<br>
* I have created database called mongoDB_assignment and collection called records.<br>
* 


### Question 1
>**Batch Create with minimum 100 records in MongoDb (create batch).**<br><br>
>*db.records.insertMany([<br>
>inserted 270 documents
*<br>

>* "insertMany()" that allows you to insert multiple documents into a collection in a single operation.i have Inserted of about 270 documents in my collection called records.
>* Acknowledgement: true - then all the inserted documents are successfully inserted.


### Question 2
>**Batch Update with minimum 100 records in MongoDB (update batch).**<br><br>
>*db.records.updateMany(<br>
>{married:"Yes"},<br>
>[{$set:<br>
>{dependent:"1"}<br>
>}]);*<br>


>* updateMany() updates all matching documents in the collection that match the filter, using the update criteria to apply modifications.
>* "$set" operator is used in update operations to modify the values of one or more fields in a document.
>* In my collection- the documents containing "married:yes" sets the value of dependents to "1" using $set .

### Question 3
>**Perform indexing on particular 3 fields in MongoDB.**<br><br>
>*db.records.createIndex({gender:1});<br>
> db.records.createIndex({LoanAmount:1});<br>
> db.records.createIndex({Education:1});*<br><br>
>* This command will create three different indexs on three different columns -
>* 1.gender:1 <br>
>* 2.loanAmount:1 <br>
>* 3.Education:1 <br>
>* Note that if we describe all indexes in one query, a compound index of all three fields will generated.<br><br>
>*db.records.createIndex({Gender:1, LoanAmount:1, Education:1});*<br><br>
>* We can see all indexes on document by this query<br><br>
>*db.records.getIndexes()*<br><br>
>* getindexes() shows all the indexes present in the collection.


### Ouestion 4
>**Find duplicates using aggregation in MongoDB**<br><br>
>*db.MongoDBAssignment.aggregate([<br>
>{"$group":{"_id":"$Loan_Status","count": {"$sum":1}}},<br>
>{"$match":{"_id" :{"$ne":null},"count":{"$gt":1}}},<br>
>{"$project":{"Loan_Status":"$_id","_id":0}}]);*<br>
>* The $group stage groups documents by a specified key and performs some kind of aggregation operation on the grouped data, such as summing or averaging values.
>* The $match stage filters the documents in the pipeline based on a specified condition. 
>* The $project stage reshapes documents in the pipeline by selecting a subset of fields, renaming fields, or creating new fields. 
>* 1.group by loan_status which concludes to grouping and using $sum we get counts of same documents
>* 2.match then filters the documents ,that if count is greater than 1 it gets matched.
>* 3.projects the loan status and shows the output of the query.

### Output of mongoDB compass connected to localhost.  
>https://simformsolutionspvtltd-my.sharepoint.com/:i:/g/personal/janvi_s_simformsolutions_com/EaFlPfC55X1JmoMNrmoalKUBW1C7LNrwTJgQ-cTuCAo1rA?email=eshan%40simformsolutions.com&e=lzBn5o <br>  
>https://simformsolutionspvtltd-my.sharepoint.com/:i:/g/personal/janvi_s_simformsolutions_com/EVG2dG_PRR1JvdBT5UoHyDEBL4BVJYrJSS2AQkSknCJ6vw?email=eshan%40simformsolutions.com&e=gcUbAQ <br>  
>https://simformsolutionspvtltd-my.sharepoint.com/:i:/g/personal/janvi_s_simformsolutions_com/ER0dzKEjUFNJrq9Am_VeEowBxCdQ97QGlN4_HdZ-HXdxsg?email=eshan%40simformsolutions.com&e=sfTdZG <br>  
>https://simformsolutionspvtltd-my.sharepoint.com/:i:/g/personal/janvi_s_simformsolutions_com/EYhc216n5FpKug5GxUTBYkAB1mxSwSv8BIeBCnP6cN1R8Q?email=eshan%40simformsolutions.com&e=Vfw8aN <br>  
>https://simformsolutionspvtltd-my.sharepoint.com/:i:/g/personal/janvi_s_simformsolutions_com/EW7P8bLHYExCgvYPqGdnE6MBiMnanRCMD8fvqkqNloE_pA?email=eshan%40simformsolutions.com&e=Lb0ywr <br>  
>https://simformsolutionspvtltd-my.sharepoint.com/:i:/g/personal/janvi_s_simformsolutions_com/EYHUxF_HxURJiWT4mKNQQQwBWKrgb-IYjMnTGR6uBV-rpw?email=eshan%40simformsolutions.com&e=vO8oyU <br> 
