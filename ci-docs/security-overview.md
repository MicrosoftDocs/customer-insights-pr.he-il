---
title: הגדרות אבטחה ב- Dynamics 365 Customer Insights
description: למד על הגדרות אבטחה ב- Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653741"
---
# <a name="security-overview-page"></a>דף מבט כולל על אבטחה

הדף **אבטחה** מפרט אפשרויות לקביעת הרשאות משתמש ותכונות שעוזרות להפוך את Dynamics 365 Customer Insights למאובטחת יותר. רק מנהלי מערכת יכולים לגשת לדף זה. 

עבור אל **מנהל מערכת** > **אבטחה** כדי לקבוע את ההגדרות.

הדף **אבטחה** כולל את הכרטיסיות הבאות:
- [משתמשים](#users-tab)
- [ממשקי API](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>כרטיסיית משתמשים

הגישה ל- Customer Insights מוגבלת למשתמשים בארגון שלך שנוספו לאפליקציה על ידי מנהל מערכת. הכרטיסיה **משתמשים** מאפשרת לך לנהל את גישת המשתמשים ואת ההרשאות שלהם. לקבלת מידע נוסף, ראה [הרשאות משתמש](permissions.md).

## <a name="apis-tab"></a>כרטיסיית ממשקשי API

הצג ונהל את המפתחות לשימוש [בממשקי ה- API של Customer Insights](apis.md) עם הנתונים מסביבה שלך.

ניתן ליצור מפתחות ראשיים ומשניים חדשים על ידי בחירה באפשרות **צור מחדש את הראשי** או **צור מחדש את המשני**. 

כדי לחסום גישת API לסביבה, בחר **השבת**. אם ממשקי API מושבתים, אפשר לבחור באפשרות **הפוך לזמין** כדי להעניק גישה שוב.

## <a name="key-vault-tab"></a>הכרטיסיה Key Vault

הכרטיסיה **Key Vault** מאפשרת לך לקשר ולנהל [Azure Key Vault](/azure/key-vault/general/basic-concepts) משלך עבור הסביבה.
ניתן להשתמש ב- key vault הייעודי כדי לאחסן סודות ולהשתמש בהם בגבול התאימות של ארגון. Customer Insights יכולות להשתמש בסודות ב- Azure Key Vault כדי [להגדיר חיבורים](connections.md) למערכות צד שלישי.

לקבלת מידע נוסף, ראה [הבאת Azure Key Vault משלך](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
