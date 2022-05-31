**Name:** Jeremy Harrod  
**Date:** 05/30/2020  
**Course:** IT FDN 130  
**GitHub:** https://github.com/JJHarrod/DBFoundations-Module07

 
# Assignment 07 – Functions
 
## Introduction
This paper will be explaining when you would use a SQL UDF, the differences and similarities between Scalar, Inline, and Multi-Statement Functions.

### Topic- When you would use a SQL UDF
These are often called User Defined Functions or just UDFs. Use UDF’s to create custom functions. There are two basic types of functions; functions that return a table of values and functions that return a single value.
### Topic- The Differences and Similarities between a Scalar, Inline, and Multi-Statement Functions
The similarities between Scalar, Inline, and Multi-Statement Functions are all functions that use parameters to return data. The differences are that a Scalar function accepts any number of parameters and returns one value. Inline functions states RETURNS TABLE and return table’s definition will be based on the function’s SELECT statement. No need to specify the structure of the return table. Multi-Statement Functions RETURNS syntax explicitly specifies the structure of the return table. This is done by declaring a TABLE variable that will be used to store and accumulate the rows that are returned as the value of the function.   

```
Create --Drop
Function dbo.fProductInventoriesWithPreviousMonthCountsWithKPIs(@KPI Int)
 Returns Table
  As
	Return (
		Select Top 100000
			p.Productname
			,p.InventoryDate
			,p.InventoryCount
			,p.PreviousMonthCount
			,p.CountVsPreviousCountKPI
		From vProductInventoriesWithPreviousMonthCountsWithKPIs as p
			Where p.CountVsPreviousCountKPI = @KPI
		);
go
```  
## Summary
In this paper we explained when you would use a SQL UDF, the differences and similarities between Scalar, Inline, and Multi-Statement Functions.
