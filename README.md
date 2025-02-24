# MongoDB Query Error: $regex operator on non-string value
This repository contains a bug report and solution for a common error in MongoDB queries involving the `$regex` operator. The error occurs when attempting to apply a regular expression to a field that does not contain a string value. This often leads to unexpected errors and incorrect query results.

## Bug Description
The `$regex` operator in MongoDB is designed to match regular expressions against string values.  If applied to a field that contains a number, object, or other non-string data type, it will throw an error. This bug demonstrates this scenario and provides a solution for robust query handling.

## Solution
The solution uses the `$expr` operator and combines it with `$type` to check the data type of the field before applying the regular expression. This ensures that the query functions correctly even if the field contains non-string values.