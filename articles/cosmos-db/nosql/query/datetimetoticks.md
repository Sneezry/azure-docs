---
title: DateTimeToTicks in Azure Cosmos DB query language
description: Learn about SQL system function DateTimeToTicks in Azure Cosmos DB.
author: seesharprun
ms.service: cosmos-db
ms.subservice: nosql
ms.topic: conceptual
ms.date: 08/18/2020
ms.author: sidandrews
ms.reviewer: jucocchi
ms.custom: query-reference, ignite-2022
---
# DateTimeToTicks (Azure Cosmos DB)
[!INCLUDE[NoSQL](../../includes/appliesto-nosql.md)]

Converts the specified DateTime to ticks. A single tick represents one hundred nanoseconds or one ten-millionth of a second. 

## Syntax
  
```sql
DateTimeToTicks (<DateTime>)
```

## Arguments
  
*DateTime*  
   UTC date and time ISO 8601 string value in the format `YYYY-MM-DDThh:mm:ss.fffffffZ`

## Return types

Returns a signed numeric value, the current number of 100-nanosecond ticks that have elapsed since the Unix epoch. In other words, DateTimeToTicks returns the number of 100-nanosecond ticks that have elapsed since 00:00:00 Thursday, 1 January 1970.

## Remarks

DateTimeDateTimeToTicks will return `undefined` if the DateTime is not a valid ISO 8601 DateTime

This system function will not utilize the index.

## Examples

Here's an example that returns the number of ticks:

```sql
SELECT DateTimeToTicks("2020-01-02T03:04:05.6789123Z") AS Ticks
```

```json
[
    {
        "Ticks": 15779342456789124
    }
]
```

Here's an example that returns the number of ticks without specifying the number of fractional seconds:

```sql
SELECT DateTimeToTicks("2020-01-02T03:04:05Z") AS Ticks
```

```json
[
    {
        "Ticks": 15779342450000000
    }
]
```

## Next steps

- [System functions Azure Cosmos DB](system-functions.yml)
- [Introduction to Azure Cosmos DB](../../introduction.md)
