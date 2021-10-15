---
title: הפעלת מדגם iOS SDK‬
description: פרוייקט לדוגמה כדי ללמוד על iOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 053e626d06d3e17b39b448987410058e45e8ae0385f3ecdef40314cb46ae4bf4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036829"
---
# <a name="run-the-ios-sdk-sample"></a>הפעלת מדגם iOS SDK‬

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

פרוייקט iOS לדוגמה זה עוזר לך להבין כיצד ה- SDK עובד באפליקציה. לא תצטרך לכתוב קוד. פשוט הוסף את מפתח הקליטה שלך ומיד תוכל לראות אירועים בסביבת העבודה שלך.

## <a name="prerequisites"></a>דרישות מוקדמות

- [Xcode גירסה 9+](https://developer.apple.com/xcode/downloads/)
- [מפתח קליטה](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>הורד את מדגם ה- iOS SDK

1. [הורד את מדגם ה- iOS SDK של תובנות לגבי מעורבות](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. חלץ את הקובץ הדחוס `ei-ios-sample.zip`.
1. פתח את פרוייקט האפליקציה לדוגמה ב- Xcode.
1. בקובץ `EIConfig.plist`, החלף את המחרוזת `“YOUR-INGESTION-KEY”` בשדה `ingestionKey` עם מפתח קליטת סביבת העבודה שלך מתובנות לגבי מעורבות תחת **מנהל מערכת** > **סביבת עבודה** > **מדריך התקנה**.
1. בחר **הפעל** כדי להתחיל את הפרוייקט לדוגמה.
1. צפה באירועים בסביבת העבודה שלך.

[!INCLUDE[footer-include](../includes/footer-banner.md)]