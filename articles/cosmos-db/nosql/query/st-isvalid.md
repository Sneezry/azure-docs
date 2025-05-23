---
title: ST_ISVALID in Azure Cosmos DB query language
description: Learn about SQL system function ST_ISVALID in Azure Cosmos DB.
author: ginamr
ms.service: cosmos-db
ms.subservice: nosql
ms.topic: conceptual
ms.date: 09/21/2021
ms.author: girobins
ms.custom: query-reference, ignite-2022
---
# ST_ISVALID (Azure Cosmos DB)
[!INCLUDE[NoSQL](../../includes/appliesto-nosql.md)]

 Returns a Boolean value indicating whether the specified GeoJSON Point, Polygon, MultiPolygon, or LineString expression is valid.  
  
## Syntax
  
```sql
ST_ISVALID(<spatial_expr>)  
```  
  
## Arguments
  
*spatial_expr*  
   Is a GeoJSON Point, Polygon, or LineString expression.  
  
## Return types
  
  Returns a Boolean expression.  
  
## Examples
  
  The following example shows how to check if a point is valid using ST_VALID.  
  
  For example, this point has a latitude value that's not in the valid range of values [-90, 90], so the query returns false.  
  
  For polygons, the GeoJSON specification requires that the last coordinate pair provided should be the same as the first, to create a closed shape. Points within a polygon must be specified in counter-clockwise order. A polygon specified in clockwise order represents the inverse of the region within it.  
  
```sql
SELECT ST_ISVALID({ "type": "Point", "coordinates": [31.9, -132.8] }) AS b 
```  
  
 Here is the result set.  
  
```json
[{ "b": false }]  
```  
> [!NOTE]
> The GeoJSON specification requires that points within a Polygon be specified in counter-clockwise order. A Polygon specified in clockwise order represents the inverse of the region within it.

## Next steps

- [System functions Azure Cosmos DB](system-functions.yml)
- [Introduction to Azure Cosmos DB](../../introduction.md)
