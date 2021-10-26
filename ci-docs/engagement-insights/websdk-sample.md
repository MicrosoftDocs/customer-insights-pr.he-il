---
title: הפעל מדגם SDK באינטרנט
description: למד כיצד להתאים אישית ולהפעיל מדגם SDK באינטרנט.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 545f4a7e9660e339dee1070ad727d5d398eb6254
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606216"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>הפעל את מדגם ה- SDK באינטרנט עבור יכולת התובנות לגבי מעורבות של Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

ספריית SDK באינטרנט של יכולת תובנות לגבי לקוחות היא ספריית JavaScript עם קוד לדוגמא שתוכלו להשתמש בו באתר שלכם.

## <a name="prerequisites"></a>דרישות מוקדמות

- התקנת [Visual Studio קוד](https://code.visualstudio.com/).
- [התקן את ההרחבה Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) בקוד של Visual Studio ולמד איך להפעיל את Live Server.
- אתה מוכרח להיות בעל [סביבת עבודה של תובנות לגבי מעורבות](create-workspace.md).

## <a name="run-sample"></a>הפעלת מדגם

1. [הורד את המדגם של SDK באינטרנט](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. חלץ את הקובץ הדחוס `ei_websdk_sample.zip`.

1. פתח את התיקיה המחולצת בקוד של Visual Studio.

1. עבור לפורטל תובנות לגבי מעורבות עבור סביבת העבודה שלך. בחר **ניהול** > **סביבת עבודה**  ולאחר מכן **מדריך התקנה**. בצע את האפשרות הראשונה ובחר **העתק קוד** כדי להעתיק את מקטע הקוד של JavaScript.

1. בקובץ`ei_websdk_sample.html`, הדבק את מקטע הקוד שהעתקת זה עתה מתחת לשורה זו:

   - <-הדבק את מקטע הקוד של JAVASCRIPT מתוך פורטל תובנות לגבי מעורבות כאן מתחת לשורה זו->

1. פתח את הקובץ `ei_websdk_sample.html` באמצעות Live Server בקוד Visual Studio קוד על ידי בחירת **עבור למצב פעיל** משורת המצב.

1. בעת פתיחת הדף, אירוע צפייה צפוי להישלח באופן אוטומטי. לחיצה על אחד מהלחצנים שבדף תשלח אירועי פעולה. הלחצן **מעקב אחר אירועים** ישלח גם אירועים מותאמים אישית. בחירת הלחצן **עבור אל Bing** תשלח אירוע פעולה לפני הניווט לאתר Bing.

1. תראה את האירועים זורמים כאשר תנווט אל סביבת העבודה שלך. סביבת עבודה זו משויכת למפתח הקליטה שהוזן בשלב 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
