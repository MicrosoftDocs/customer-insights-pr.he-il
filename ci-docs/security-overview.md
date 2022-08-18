---
title: קבע את הגדרות האבטחה
description: למד על הגדרות אבטחה ב- Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ea21163d7dd05370de28ca8340ae9583846adb26
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246063"
---
# <a name="configure-security-settings"></a>קבע את הגדרות האבטחה

נהל מפתחות API, גש לנתוני לקוחות והגדר קישור פרטי של Azure.

## <a name="manage-api-keys"></a>נהל מפתח API

הצג ונהל את המפתחות לשימוש [בממשקי ה- API של Customer Insights](apis.md) עם הנתונים בסביבה שלך.

1. עבור אל **מערכת** > **אבטחה**, ולאחר מכן בחר בכרטיסיה **ממשקי API**.

1. אם לא הוגדרה גישת API לסביבה, בחר **הפוך לזמין**. לחלופין, כדי לחסום גישת API לסביבה, בחר **השבת** ואשר.

1. נהל את מפתחות ה- API הראשיים והמשניים:

   1. כדי להציג את מפתח ה-API הראשי או המשני, בחר בסמל **הצג**.

   1. כדי להעתיק את מפתח ה-API הראשי או המשני, בחר בסמל **העתק**.

   1. כדי ליצור מפתחות ראשיים ומשניים חדשים של ה- API, בחר באפשרות **צור מחדש את הראשי** או **צור מחדש את המשני**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>גישה מאובטחת לנתוני לקוח באמצעות כספת לקוח (‏Preview)

Customer Insights משתמש ביכולת כספת לקוח של Power Platform. כספת לקוח מספק ממשק לבדיקה ואישור (או דחיית) של בקשות גישה לנתונים. בקשות אלו מתרחשות כאשר יש צורך בגישה לנתונים של לקוחות כדי לפתור מקרה תמיכה. כדי להשתמש בתכונה זו, ל- Customer Insights נדרש חיבור קיים לסביבת Microsoft Dataverse בדייר שלך.

למידע נוסף על כספת לקוח, עיין ב[סיכום](/power-platform/admin/about-lockbox#summary) כספת לקוח של Power Platform. המאמר מתאר גם את [זרימת העבודה](/power-platform/admin/about-lockbox#workflow) ואת [ההגדרה](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) הנדרשת להפיכת כספת לקוח לזמין.

> [!IMPORTANT]
> מנהלים כלליים של Power Platform או מנהלי מערכת של Power Platform יכולים לאשר בקשות של כספת לקוח שהונפקו עבור Customer Insights.

## <a name="set-up-an-azure-private-link"></a>הגדר קישור פרטי של Azure

[קישור פרטי של Azure](/azure/private-link/private-link-overview) מאפשר ל- Customer Insights להתחבר אל חשבון Azure Data Lake Storage שלך באמצעות נקודת קצה פרטית ברשת הוירטואלית שלך. עבור נתונים בחשבון אחסון שאינו חשוף לאינטרנט הציבורי, קישור פרטי מאפשר את החיבור לרשת מוגבלת זו.

> [!IMPORTANT]
> דרישת תפקיד מינימלית להגדרת חיבור קישור פרטי:
>
> - Customer Insights: מנהל מערכת
> - תפקיד מובנה של Azure: [חשבון אחסון משתתף](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - הרשאות עבור תפקיד Azure מותאם אישית: [ Microsoft.Storage/storageAccounts/read ו-Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. ב- Customer Insights, עבור אל **מנהל מערכת** > **אבטחה** ובחר סכרטיסיה **קישורים פרטיים**.

1. בחר **הוסף קישור פרטי**.

   החלונית **הוסף קישור פרטי** מציגה חשבונות אחסון מהדייר שלך שיש לך הרשאות לראות.

1. בחר את מינוי, קבוצת משאבים וחשבון אחסון.

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **Save**.

1. עבור לחשבון Data Lake Storage שלך ופתח את הקישור המוצג על המסך.

1. אשר את הקישור הפרטי.


[!INCLUDE [footer-include](includes/footer-banner.md)]
