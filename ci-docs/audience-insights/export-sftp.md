---
title: ייצוא נתוני Customer Insights אל מארחי SPTF
description: למד כיצד להגדיר את החיבור אל מארח SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643504"
---
# <a name="connector-for-sftp-preview"></a>מחבר עבור SFTP‏ (Preview)

השתמש בנתוני הלקוחות שלך ביישומי צד שלישי על-ידי ייצוא שלהם אל מארח Secure File Transfer Protocol‏ (SFTP).

## <a name="prerequisites"></a>דרישות מוקדמות

- זמינות של מארח SFTP ואישורים מתאימים.

## <a name="connect-to-sftp"></a>התחברות ל- SFTP

1. עבור אל **מנהל** > **יעדי ייצוא**.

1. ב- **SFTP**, בחר **הגדר**.

1. תן ליעד שלך שם הניתן לזיהוי בשדה **שם תצוגה**.

1. ספק **שם משתמש**, **סיסמה** ו **שם מארח** עבור חשבון SPTF שלך. דוגמה: אם תיקיית הבסיס של שרת SPTF שלך היא /root/folder, וברצונך לבצע ייצוא של הנתונים אל /root/folder/ci_export_destination_folder, המארח צריך להיות sftp://<server_address>/ci_export_destination_folder".

1. בחר **אימות** כדי לבדוק את החיבור.

1. לאחר אימות מוצלח, בחר אם ברצונך לייצא את הנתונים כשהם **מכווצים** או **לא מכווצים**, ובחר את **מפריד בין שדות** עבור הקבצים המיוצאים.

1. בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.

1. בחר **הבא** כדי להתחיל בהגדרת הייצוא.

## <a name="configure-the-connection"></a>הגדרת החיבור

1. בחר **תכונות לקוח** שברצונך לייצא. ניתן לייצא תכונה אחת או כמה תכונות.

1. בחר **הבא**.

1. בחר את הפלחים שברצונך לייצא.

1. בחר **שמור**.

## <a name="export-the-data"></a>ייצוא הנתונים

באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md). הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים דרך SPTF, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא שיעד הייצוא עומד בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.
