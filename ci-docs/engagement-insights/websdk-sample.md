---
title: הפעל מדגם SDK באינטרנט
description: למד כיצד להתאים אישית ולהפעיל מדגם SDK באינטרנט.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036604"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>הפעל את מדגם ה- SDK באינטרנט עבור יכולת התובנות לגבי מעורבות של Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

ספריית SDK באינטרנט של יכולת תובנות לגבי לקוחות היא ספריית JavaScript עם קוד לדוגמא שתוכלו להשתמש בו באתר שלכם.

## <a name="prerequisites"></a>דרישות מוקדמות

- התקנת [Visual Studio קוד](https://code.visualstudio.com/).
- [התקן את ההרחבה Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) בקוד של Visual Studio ולמד איך להפעיל את Live Server.
- עליך להחזיק ב[מפתח הקליטה](instrument-website.md).

## <a name="run-sample"></a>הפעלת מדגם

1. [הורד את המדגם של SDK באינטרנט](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. חלץ את הקובץ הדחוס `ei_websdk_sample.zip`.

1. פתח את התיקיה המחולצת בקוד של Visual Studio.

1. בתוך קובץ `ei_websdk_sample.html`, החלף את המחרוזת "INGESTION_KEY" במפתח הקליטה שלך מפורטל יכולת התובנות לגבי מעורבות, ואת המחרוזת "NAME" עם השם הכללי שבו תרצה ליצור את מופע ה- SDK. ודא שהחלפת את כל המופעים.

1. פתח את הקובץ `ei_websdk_sample.html` באמצעות Live Server בקוד Visual Studio קוד על ידי בחירת **עבור למצב פעיל** משורת המצב.

1. בעת פתיחת הדף, אירוע צפייה צפוי להישלח באופן אוטומטי. לחיצה על אחד מהלחצנים שבדף תשלח אירועי פעולה. הלחצן **מעקב אחר אירועים** ישלח גם אירועים מותאמים אישית. בחירת הלחצן **עבור אל Bing** תשלח אירוע פעולה לפני הניווט לאתר Bing.

1. תראה את האירועים זורמים כאשר תנווט אל סביבת העבודה שלך. סביבת עבודה זו משויכת למפתח הקליטה שהוזן בשלב 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]