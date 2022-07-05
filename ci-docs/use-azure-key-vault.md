---
title: הבאת Azure Key Vault משלך (Preview)
description: למד כיצד להגדיר את Customer Insights לשימוש ב- Azure Key Vault משלך לניהול סודות.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 8fdb131de35c7d936d2921265f03faa5682db6f6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081477"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>הבאת Azure Key Vault משלך (Preview)

קישור [Azure Key Vault](/azure/key-vault/general/basic-concepts) ייעודי לסביבת Customer Insights עוזר לארגונים לעמוד בדרישות התאימות.
ניתן להשתמש ב- key vault הייעודי כדי לאחסן סודות ולהשתמש בהם בגבול התאימות של ארגון. Customer Insights יכולות להשתמש בסודות ב- Azure Key Vault כדי [להגדיר חיבורים](connections.md) למערכות צד שלישי.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>קישור ה- Key Vault לסביבת Customer Insights

### <a name="prerequisites"></a>דרישות מוקדמות

כדי להגדיר את ה- key vault ב- Customer Insights, יש לעמוד בתנאים המוקדמים הבאים:

- יש לך מנוי Azure פעיל.

- יש לך תפקיד [מנהל מערכת](permissions.md#admin) ב- Customer Insights. מידע נוסף בנושא [הרשאות משתמש ב- Customer Insights](permissions.md#assign-roles-and-permissions).

- אתה בעל התפקידים [משתתף](/azure/role-based-access-control/built-in-roles#contributor) ו[מנהל גישת משתמשים](/azure/role-based-access-control/built-in-roles#user-access-administrator) ב- key vault או בקבוצת המשאבים שאליה משתייך ה- key vault. לקבלת מידע נוסף, עבור אל [הוספה או הסרה של הקצאות תפקיד Azure באמצעות פורטל Azure](/azure/role-based-access-control/role-assignments-portal). אם אין לך את התפקיד 'מנהל גישת משתמשים' ב- key vault, עליך להגדיר את הרשאות בקרת הגישה המבוססות על תפקידים עבור מנהל שירות Azure עבור Dynamics 365 Customer Insights בנפרד. בצע את השלבים כדי [להשתמש במנהל שירות Azure](connect-service-principal.md) עבור ה- key vault שצריך לקשר.

- ב- key vault, חומת האש של ה- key vault מוכרחה להיות **מושבתת**.

- ה- key vault נמצא באותו [מיקום Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) כמו סביבת Customer Insights. אזור הסביבה ב- Customer Insights מופיע תחת **מנהל מערכת** > **מערכת** > **אודות** > **אזור**.

### <a name="link-a-key-vault-to-the-environment"></a>קישור key vault לסביבה

1. עבור אל **מנהל מערכת** > **אבטחה**, ולאחר מכן בחר את הכרטיסיה **Key Vault**.
1. באריח **Key Vault**, בחר **הגדרה**.
1. בחר **מנוי**.
1. בחר key vault מהרשימה הנפתחת **Key Vault**. אם מוצגים יותר מדי רכיבי Key Vault, בחר קבוצת משאבים כדי להגביל את תוצאות החיפוש.
1. קבל את הצהרת **פרטיות נתונים ותאימות**.
1. בחר **Save**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="שלבים להגדרת Key Yault מקושר ב- Customer Insights.":::

האריח **Key Vault** מציג כעת את שם ה- key vault המקושר, את קבוצת המשאבים ואת המנוי. הוא מוכן לשימוש בהגדרת החיבור.
לקבלת פרטים לגבי ההרשאות ב- key vault שמוענקות ל- Customer Insights, עבור אל [הרשאות שניתנות ב- Key Vault ל- Customer Insights](#permissions-granted-on-the-key-vault) בהמשך המאמר.

## <a name="use-the-key-vault-in-the-connection-setup"></a>שימוש ב- key vault בהגדרת החיבור

בעת [הגדרת חיבורים](connections.md) למערכות צד שלישי, הסודות מה- Key Vault המקושר יכולים לשמש להגדרת החיבורים.

1. עבור אל **ניהול** > **חיבורים**.
1. בחר **הוסף חיבור**.
1. עבור סוגי החיבור הנתמכים, לחצן דו-מצבי של **השתמש ב- Key Vault** זמין אם קישרת key vault.
1. במקום להזין את הסוד באופן ידני, באפשרותך לבחור את שם הסוד שמצביע על ערך הסוד ב- key vault.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="חלונית חיבור עם חיבור SFTP שמשתמשת בסוד Key Vault.":::

## <a name="supported-connection-types"></a>סוגי חיבור נתמכים

חיבורי [הייצוא](export-destinations.md) הבאים נתמכים:

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>הרשאות שניתנו ב-Key Vault

ההרשאות הבאות ניתנות ל- Customer Insights ב- Key Vault מקושר אם [מדיניות הגישה של Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) או [בקרת גישה מבוססת-תפקיד של Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) זמינות.

### <a name="key-vault-access-policy"></a>מדיניות גישה של Key Vault

| סוג        | הרשאות          |
| ----------- | -------------------- |
| מקש         | [קבלת מפתחות](/rest/api/keyvault/keys/get-keys/get-keys), [קבלת מפתח](/rest/api/keyvault/keys/get-key/get-key)                                 |
| סוד      | [קבלת סודות](/rest/api/keyvault/secrets/get-secrets/get-secrets), [קבלת סוד](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| אישור | [קבלת אישורים](/rest/api/keyvault/certificates/get-certificates/get-certificates), [קבלת אישור](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

הערכים הקודמים הם המינימום שצריך לפרט ולקרוא במהלך הביצוע.

### <a name="azure-role-based-access-control"></a>בקרת גישה מבוססת-תפקידים של Azure

תפקידי המשתמש 'קורא' ו'סודות' של Key Vault יתווספו עבור Customer Insights. לקבלת פרטים אודות תפקידים אלה, עבור אל [תפקידים מוכללים של Azure עבור פעולות מישור נתונים של Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>המלצות

- השתמש ב- Key Vault נפרד או ייעודי שמכיל את הסודות הנדרשים עבור Customer Insights. קרא עוד על הסיבה לכך [שרכיבי key vault נפרדים מומלצים](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- עקוב אחר [שיטות העבודה המומלצות לשימוש ב- Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) עבור אפשרויות בקרת גישה, גיבוי, ביקורת ושחזור.

## <a name="frequently-asked-questions"></a>שאלות נפוצות

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>האם Customer Insights יכולות לכתוב סודות או להחליף סודות ב- Key Vault?

לא. רק הרשאות הקריאה ורשימה המופיעות במקטע [הרשאות שהוענקו](#permissions-granted-on-the-key-vault) שמופיע לעיל במאמר זה מוענקות ל- Customer Insights. המערכת לא יכולה להוסיף, למחוק או להחליף סודות ב- key vault. זו גם הסיבה לכך שלא ניתן להזין אישורים כאשר חיבור משתמש ב- Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>האם ניתן לשנות חיבור משימוש בסודות Key Vault לאימות ברירת מחדל?

לא. אין באפשרותך לחזור לחיבור ברירת המחדל לאחר שהגדרת אותו באמצעות סוד מתוך key vault מקושר. צור חיבור נפרד, ומחק את החיבור הישן אם אינך זקוק לו עוד.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>כיצד ניתן לבטל את הגישה ל- Key Vault עבור Customer Insights?

תלוי אם [מדיניות גישה ל- Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) או [בקרת גישה מבוססת-תפקיד של Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) מופעלת, עליך להסיר את ההרשאות עבור מנהל השירות `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` בשם `Dynamics 365 AI for Customer Insights`. כל החיבורים שמשתמשים ב- key vault יפסיקו לעבוד.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>סוד המשמש בחיבור הוסר מ- key vault. מה אני יכול לעשות?

הודעה מופיעה ב- Customer Insights כאשר סוד מוגדר מ- key vault אינו נגיש עוד. הפוך את האפשרות [מחיקה זמנית](/azure/key-vault/general/soft-delete-overview) לזמינה ב- key vault כדי לשחזר סודות אם הוסרו בשוגג.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>חיבור לא פועל, אבל הסוד שלי נמצא ב- key vault. מה יכולה להיות הסיבה?

הודעה מופיעה ב- Customer Insights כאשר היא אינה יכולה לגשת ל- key vault. הסיבה עשויה להיות:

- ההרשאות למנהל השירות של Customer Insights הוסרו. יש לשחזר אותן ידנית.

- חומת האש ב- key vault מופעלת. יש להשבית את חומת האש כדי להפוך את ה- key vault לנגיש שוב עבור Customer Insights.
