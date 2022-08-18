---
title: תשתמש בחשבון Azure Data Lake Storage‏ Gen2 משלך
author: mukeshpo
description: למד על הדרישות לשימוש בחשבון Azure Data Lake Storage משלך לאחסון נתוני Customer Insights.
ms.author: mukeshpo
ms.date: 06/08/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: d2ff49c324c5c5c28213f362ff330d441fcb6052
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246202"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>תשתמש בחשבון Azure Data Lake Storage‏ Gen2 משלך

Dynamics 365 Customer Insights מאפשר לך לאחסן את כל הנתונים שלך ב- [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction).

בכך שאתה שומר נתונים ב- Data Lake Storage, אתה מסכים לכך שהנתונים יועברו ויישמרו במיקום הגיאוגרפי המתאים עבור אותו חשבון אחסון של Azure. לקבלת מידע נוסף, ראה [מרכז יחסי האימון של Microsoft](https://www.microsoft.com/trust-center)

מנהלי מערכת ב- Customer Insights יכולים [ליצור סביבות](create-environment.md) ו[לציין את אפשרות אחסון הנתונים](create-environment.md#step-2-configure-data-storage) תוך כדי כך.

## <a name="prerequisites-to-use-your-storage-account"></a>דרישות מקדימות לשימוש בחשבון האחסון שלך

- חשבונות Azure Data Lake Storage חייבים להיות באותו אזור של Azure שבחרת בעת יצירת הסביבה של Customer Insights. ניתן לבדוק את האזור של סביבת Customer Insights תחת **מנהל מערכת** > מ **ערכת** > **אודות**.
- על החשבון Azure Data Lake Storage להיות Gen 2 והתכונה ['מרחב שמות הירארכי' צריכה להיו זמינה](/azure/storage/blobs/create-data-lake-storage-account). חשבונות אחסון מסוג Gen1 אינם נתמכים.
- מיכל בשם `customerinsights` חייב להתקיים בחשבון האחסון. עליך ליצור אותו לפני השימוש באחסון Data Lake משלך ב- Customer Insights. מנהל מערכת שמגדיר את סביבת Customer Insights זקוק לתפקיד 'משתתף של נתוני Blob של אחסון' או 'בעלים של נתוני Blob של אחסון' בחשבון האחסון או גורם המכיל `customerinsights`. למידע נוסף על הקצאת הרשאות בחשבון אחסון, ראה [צור חשבון אחסון](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>חבר את Customer Insights לחשבון האחסון שלך

כאשר אתה יוצר סביבה חדשה, ודא שחשבון Data Lake Storage קיים ושכל התנאים המוקדמים מתקיימים.

1. בשלב **אחסון נתונים** במהלך יצירת הסביבה, הגדר **שמור נתוני פלט** ל **Azure Data Lake Storage Gen2**.
1. בחר כיצד **לחבר את האחסון שלך**. אתה יכול לבחור בין אפשרות מבוססת משאבים לאפשרות המבוססת על מנוי לאימות. לקבלת מידע נוסף, ראה [התחברות לחשבון Azure Data Lake Storage באמצעות מנהל שירות של Azure](connect-service-principal.md).
   - עבור **מינוי Azure**, בחר ב **מינוי**, ב **קבוצת המשאבים**, וב **חשבון האחסון** שמכילים את הגורם המכיל `customerinsights`.
   - ל **מפתח חשבון**, ספק את **שם החשבון** ואת **מפתח החשבון** עבור חשבון Data Lake Storage. שימוש בשיטת אימות לגרום לכך שתקבל הודעה אם הארגון שלך עושה סבב עם המפתחות. אתה חייב [עדכן את תצורת הסביבה](manage-environments.md#edit-an-existing-environment) עם המפתח החדש כאשר מתבסס סבב.
1. בחר אם ברצונך להשתמש בקישור פרטי של Azure  כדי להתחבר לחשבון האחסון ו[צור את החיבור לקישור פרטי](security-overview.md#set-up-an-azure-private-link) באמצעות תהליך דו-שלבי.

כאשר תהליכי מערכת, כמו עיבוד נתונים מסתיימים, המערכת יוצרת תיקיות מתאימות בחשבון האחסון שציינת. קבצי נתונים וקבצי *model.json* נוצרים ונוספים לתיקיות בהתאם לשם התהליך.

אם אתה יוצר סביבות מרובות של Customer Insights ובוחר לשמור את ישויות הפלט מסביבות אלה בחשבון האחסון שלך, Customer Insights יוצר תיקיות נפרדות לכל סביבה עם `ci_environmentID` בגורם המכיל.
