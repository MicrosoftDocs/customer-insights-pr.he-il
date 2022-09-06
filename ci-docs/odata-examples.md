---
title: דוגמאות לשאילתות OData עבור ממשקי API של Customer Insights
description: דוגמאות נפוצות של פרוטוקול הנתונים הפתוח (OData) לשאילתה של ממשקי ה-API של Customer Insights כדי לסקור נתונים.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 26e56a3bab01ba55284a52e72efbcbfbaadaad6f
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387203"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>דוגמאות לשאילתות OData עבור ממשקי API של Customer Insights

פרוטוקול הנתונים הפתוח (OData) הוא פרוטוקול גישה לנתונים הבנוי על פרוטוקולי ליבה כמו HTTP. הוא משתמש במתודולוגיות מקובלות כמו REST עבור האינטרנט. ישנם סוגים שונים של ספריות וכלים שניתן להשתמש בהם כדי לצרוך שירותי OData.

כדי לעזור לך בבניית יישומים משלך בהתבסס על [ממשקי API של Customer Insights](apis.md), תוכל לסקור כמה שאילתות לדוגמה שנשלחות לעתים קרובות.

שנה את דוגמאות השאילתה כדי לגרום להם לעבוד על סביבות היעד:

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` כאשר {instanceId} הוא ה- GUID של סביבת Customer Insights שברצונך לבצע שאילתה. האפשרות [פעולת ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) מאפשרת לך למצוא {InstanceId} שיש לך גישה אליו.
- {CID}: ‏GUID של רשומת לקוח מאוחדת. דוגמה:`ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: מזהה של המפתח הראשי של רשומת לקוח במקור נתונים. דוגמה: `CNTID_1002`
- {DSname}: מחרוזת עם שם הישות של מקור נתונים שנכנסת ל-Customer Insights. דוגמה:`Website_contacts`.
- {SegmentName}: מחרוזת עם שם ישות הפלט של פלח ב- Customer Insights. דוגמה:`Male_under_40`.

## <a name="customer"></a>לקוח

שאילתות לדוגמה עבור הישות *צרכן*.

|סוג שאילתה |דוגמה  | הערה  |
|---------|---------|---------|
|מזהה לקוח אחד     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|מפתח חלופי    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  מפתחות חלופיים נשארים בישות הלקוח המאוחדת       |
|בחר   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|בעוד    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|מפתח חלופי + In   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|חיפוש  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   מחזירה את 10 התוצאות המובילות עבור מחרוזת חיפוש      |
|חברות בפלח  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | מחזירה מספר שורות מוגדר מראש מיישות הפילוח.      |
|חברות בפלח עבור לקוח | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | מחזירה את פרופיל הלקוח אם הוא חבר בפלח הנתון     |

## <a name="unified-activity"></a>פעילות מאוחדת

שאילתות לדוגמה עבור הישות *UnifiedActivity*.

|סוג שאילתה |דוגמה  | הערה  |
|---------|---------|---------|
|פעילות של CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | מפרט פעילויות של פרופיל לקוח ספציפי |
|מסגרת זמן הפעילות    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  פעילויות של פרופיל לקוח במסגרת זמן       |
|סוג פעילות    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|פעילות לפי שם תצוגה     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|מיון פעילות    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  מיין פעילויות בסדר עולה או יורד       |
|הפעילות הורחבה מחברות בפלח  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>דוגמאות אחרות

שאילתות לדוגמה עבור ישויות אחרות.

|סוג שאילתה |דוגמה  | הערה  |
|---------|---------|---------|
|מדדים של CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|מותגים מועשרים של CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|תחומי עניין מועשרים של CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-Clause + Expand     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>שאילתות OData לא נתמכות

השאילתות הבאות אינן נתמכות על ידי Customer Insights:

- `$filter` על ישויות מקור שנטמעו. אתה יכול להריץ שאילתות ‏$‎‏filter‎‏ רק על ישויות מערכת ש- Customer Insights יוצר.
- `$expand` מתוך שאילתת `$search`. דוגמה: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` מ- `$select` אם רק קבוצת משנה של תכונות נבחרה. דוגמה: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` זיקה מועשרת למותג או לתחומי עניין עבור לקוח נתון. דוגמה: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- שאילתת חיזוי ישויות פלט של מודל דרך מפתח חלופי. דוגמה: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
