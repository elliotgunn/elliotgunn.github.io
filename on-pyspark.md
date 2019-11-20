



[Data Wrangling with PySpark for Data Scientists Who Know Pandas - Andrew Ray](https://www.youtube.com/watch?v=XrpSRCwISdk)
- PySpark: great if you already know Python & Pandas, love dataframes, need to work with big data
- Pros: SQL
- Cons: lose indices, easy plotting
- Important:
	- Immutable: changes create new object, old version unchanged
	- Lazy: compute does not happen until output is requested
- Steps (Pandas vs PySpark):
	1. Load csv
		- `df = pd.read_csv("test.csv")`
		- df = spark.read.csv("test.csv").options(header=True, inferSchema=True)
	2. View dataframe
		- df
		- df.show()
	3. Columns and datatypes
		- both: df.columns, df.dtypes
	4. Rename columns
		- df.columns = ['a', 'b', 'c']
		- df.toDF('a', 'b', 'c']
	5. Rename columns
		- df.rename(columns = {'old': 'new'})
		- df.withColumnRenamed('old', 'new')
	6. Drop column
		- df.drop('mpg', axis=1)
		- df.drop('mpg')
	7. Filtering
		- both: df[df.mpg < 20], df[(df.mpg < 20) & (df.cyl == 6)]
	8. Add column
		- df['gym'] = 1 / df.mpg
		- df.withColumn('gym', 1 / df.mpg)
	9. Fill nulls
		- df.fillna(0)
	10. Aggregation
		- df.groupby(['cyl', 'gear']).agg({'mpg': 'mean', 'disp': 'min'})

Standard transformations (with built in functions)
Pandas  
```import numpy as np  
df['logdisp'] = np.log(df.disp)``` 
PySpark  
```import pyspark.sql.functions as F 
df.withColumn('logdisp', F.log(d.disp))```

Row Conditional Statements
Pandas
`df['cond']=df.apply(lambda r: 1 if r.mpg > 20 else 2 if r.cyl == 6 else 3, axis=1)` 
PySpark
```import pyspark.sql.functions as F  
df.withColumn('cond', F.when(df.mpg > 20, 1).when(df.cyl == 6, 2).otherwise(3))```

Python when required
Pandas
df['disp1'] = df.disp.apply(lambda x: x+1)
PySpark
```import pyspark.sql.functions as F 
from pyspark.sql.types import DoubleType
fn = F.udf(lambda x: x+1, DoubleType()) # register it as a udf
df.withColumn('disp1', fn(df.disp))
```

Merge/Join Dataframes
- left.merge(right, on='key')
- left.join(right, on='key')

Summary Statistics
- df.describe()
- df.describe().show()

SQL (PySpark only)
```df.createOrReplaceTempView('foo')
df2 = spark.sql('select * from foo')```

Best practices
- Use pyspark.sql.functions and other built-in functions
- Use the same version of python and packages on cluster as drive (e.g. Conda environment)
- Check out the built-in UI at http://localhost:4040/
- Learn about SSH port forwarding when you're running notebooks on a cluster
- Check out Spark MLlib

Things not to do
- Iterate through rows
- df.toPandas().head()
  - instead do: df.limit(5).toPandas()


[PySpark Dataframes Tutorial | Introduction to PySpark Dataframes API | PySpark Training | Edureka](https://www.youtube.com/watch?v=dq73Ghk3MQg)
- What are dataframes?
  - 

[RegExr](https://regexr.com/)
