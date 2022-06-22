---
title: הגדרות אבטחה ב- Customer Insights
description: למד על הגדרות אבטחה ב- Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947416"
---
# <a name="security-settings-in-customer-insights"></a>הגדרות אבטחה ב- Customer Insights

הדף **אבטחה** מפרט אפשרויות לקביעת הרשאות משתמש ותכונות שעוזרות להפוך את Dynamics 365 Customer Insights למאובטחת יותר. רק מנהלי מערכת יכולים לגשת לדף זה.

עבור אל **מנהל מערכת** > **אבטחה** כדי לקבוע את ההגדרות.

הדף **אבטחה** כולל את הכרטיסיות הבאות:

- [משתמשים](#users-tab)
- [ממשקי API](#apis-tab)
- [קישורים פרטיים](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [גישה מאובטחת לנתוני לקוח באמצעות כספת לקוח (‏Preview)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>כרטיסיית משתמשים

הגישה ל- Customer Insights מוגבלת למשתמשים בארגון שלך שנוספו לאפליקציה על ידי מנהל מערכת. הכרטיסיה **משתמשים** מאפשרת לך לנהל את גישת המשתמשים ואת ההרשאות שלהם. לקבלת מידע נוסף, ראה [הרשאות משתמש](permissions.md).

## <a name="apis-tab"></a>כרטיסיית ממשקשי API

הצג ונהל את המפתחות לשימוש [בממשקי ה- API של Customer Insights](apis.md) עם הנתונים מסביבה שלך.

ניתן ליצור מפתחות ראשיים ומשניים חדשים על ידי בחירה באפשרות **צור מחדש את הראשי** או **צור מחדש את המשני**. 

כדי לחסום גישת API לסביבה, בחר **השבת**. אם ממשקי API מושבתים, אפשר לבחור באפשרות **הפוך לזמין** כדי להעניק גישה שוב.

## <a name="private-links-tab"></a>כרטיסיית קישורים פרטיים

[קישור פרטי של Azure](/azure/private-link/private-link-overview) מאפשר ל- Customer Insights להתחבר אל חשבון Azure Data Lake Storage שלך באמצעות נקודת קצה פרטית ברשת הוירטואלית שלך. עבור נתונים בחשבון אחסון שאינו חשוף לאינטרנט הציבורי, קישור פרטי מאפשר את החיבור לרשת מוגבלת זו.

> [!IMPORTANT]
> דרישת תפקיד מינימלית להגדרת חיבור קישור פרטי:
>
> - Customer Insights: מנהל מערכת
> - תפקיד מובנה של Azure: [חשבון אחסון משתתף](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - הרשאות עבור תפקיד Azure מותאם אישית: [ Microsoft.Storage/storageAccounts/read ו-Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

הגדרת קישור פרטי ב- Customer Insights היא תהליך בן שני שלבים. ראשית, אתה יוזם יצירת קישור פרטי דרך **מנהל מערכת** > **אבטחה** > **קישורים פרטיים** ב- Customer Insights. החלונית **הוסף קישור פרטי** מציגה חשבונות אחסון מהדייר שלך שיש לך הרשאות לראות. בחר את חשבון האחסון וספק הסכמה ליצירת הקישור הפרטי.

לאחר מכן, עליך לאשר את הקישור הפרטי בצד חשבון Data Lake Storage. פתח את הקישור המוצג על המסך כדי לאשר את הקישור הפרטי החדש.

## <a name="key-vault-tab"></a>הכרטיסיה Key Vault

הכרטיסיה **Key Vault** מאפשרת לך לקשר ולנהל [Azure Key Vault](/azure/key-vault/general/basic-concepts) משלך עבור הסביבה.
ניתן להשתמש ב- key vault הייעודי כדי לאחסן סודות ולהשתמש בהם בגבול התאימות של ארגון. Customer Insights יכולות להשתמש בסודות ב- Azure Key Vault כדי [להגדיר חיבורים](connections.md) למערכות צד שלישי.

לקבלת מידע נוסף, ראה [הבאת Azure Key Vault משלך](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>גישה מאובטחת לנתוני לקוח באמצעות כספת לקוח (‏Preview)

Customer Insights משתמש ביכולת כספת לקוח של Power Platform. כספת לקוח מספק ממשק לבדיקה ואישור (או דחיית) של בקשות גישה לנתונים. בקשות אלו מתרחשות כאשר יש צורך בגישה לנתונים של לקוחות כדי לפתור מקרה תמיכה. כדי להשתמש בתכונה זו, ל- Customer Insights נדרש חיבור קיים לסביבת Microsoft Dataverse בדייר שלך.

למידע נוסף על כספת לקוח, עיין ב[סיכום](/power-platform/admin/about-lockbox#summary) כספת לקוח של Power Platform. המאמר מתאר גם את [זרימת העבודה](/power-platform/admin/about-lockbox#workflow) ואת [ההגדרה](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) הנדרשת להפיכת כספת לקוח לזמין.

> [!IMPORTANT]
> מנהלים כלליים של Power Platform או מנהלי מערכת של Power Platform יכולים לאשר בקשות של כספת לקוח שהונפקו עבור Customer Insights.

[!INCLUDE [footer-include](includes/footer-banner.md)]
