---
title: REVERSE in Azure Cosmos DB query language
description: Learn about SQL system function REVERSE in Azure Cosmos DB.
author: ginamr
ms.service: cosmos-db
ms.subservice: nosql
ms.topic: conceptual
ms.date: 03/03/2020
ms.author: girobins
ms.custom: query-reference, ignite-2022
---
# REVERSE (Azure Cosmos DB)
[!INCLUDE[NoSQL](../../includes/appliesto-nosql.md)]

 Returns the reverse order of a string value.  
  
## Syntax
  
```sql
REVERSE(<str_expr>)  
```  
  
## Arguments
  
*str_expr*  
   Is a string expression.  
  
## Return types
  
  Returns a string expression.  
  
## Examples
  
  The following example shows how to use `REVERSE` in a query.  
  
```sql
SELECT REVERSE("Abc") AS reverse  
```  
  
 Here is the result set.  
  
```json
[{"reverse": "cbA"}]  
```  

## Remarks

This system function will not utilize the index.

## Next steps

- [System functions Azure Cosmos DB](system-functions.yml)
- [Introduction to Azure Cosmos DB](../../introduction.md)
