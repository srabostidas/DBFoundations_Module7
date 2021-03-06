Puja Das
03/04/21
IT FDN 130
Assignment 07
SQL UDF and Differences Among them
Introduction: This module discussed UDF’s and and some of the differences among scalar, inline and multi-statement functions. 

When to use a SQL UDF:
As discussed last week, SQL server has built-in functions as well as custom functions and those custom functions can be called User Defined Functions. There are two basic types: functions that return a table of values and functions that return only a single value. UDFs can be used to Check Constraints. In plain words, if there is a condition that is above a certain integer, you get one thing, and if it is below, you get another thing. It does not always have to be an integer. Figure 1 shows how we configure a before and after meeting time in the function by placing the true and false phrases within parenthesis depending on whether the condition is met or not. This is why, when the column shows True, the column right by it says ‘Before start’ . Same goes with the row below them.

SELECT dbo.fGetMeetingDateTime(1);
SELECT IIF(CAST('1/1/2020 07:00:00' as datetime) < dbo.fGetMeetingDateTime(1), 'TRUE', 'FALSE'),'Before Start';
SELECT IIF(CAST('1/1/2020 11:00:00' as datetime) < dbo.fGetMeetingDateTime(1), 'TRUE', 'FALSE'), 'After Start';
Go

Figure 1 - example of a function test

Differences between Scalar, Inline, Multi-Statement Functions:
UDFs can return a single scalar value that can be especially useful when using parameters. For example, you can insert two integers into the function and have them multiply to get an integer. 
Inline functions are also a UDF but they return their results in a table and as such, can be queried like usual. They can include many parameters.
Multi-statement functions, much like the name suggests, consists of many statements that can have specifications of the return variable at the top of the function. Inline functions do not have this. They also have Begin and End statements, which Scalar and Inline functions do not use. 



Summary: There are several types of UDFs that can be used based on the number of parameters and other specifications that the user may have. Another consideration is what kind of return method is wanted - a table or simply values. 

https://github.com/srabostidas/DBFoundations_Module7


References

Module Notes and videos
https://database.guide/introduction-to-multi-statement-table-valued-functions-mstvf-in-sql-server/

