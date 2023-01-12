---
UID: NF:winsplp.ReplyPrinterChangeNotificationEx
title: ReplyPrinterChangeNotificationEx function (winsplp.h)
description: Describes the ReplyPrinterChangeNotificationEx function.
old-location: print\replyprinterchangenotificationex.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["ReplyPrinterChangeNotificationEx function"]
ms.keywords: ReplyPrinterChangeNotificationEx, ReplyPrinterChangeNotificationEx function [Print Devices], print.replyprinterchangenotificationex, winsplp/ReplyPrinterChangeNotificationEx
req.header: winsplp.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - ReplyPrinterChangeNotificationEx
 - winsplp/ReplyPrinterChangeNotificationEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Winsplp.h
api_name:
 - ReplyPrinterChangeNotificationEx
---

## -description

Describes the **ReplyPrinterChangeNotificationEx** function.

## -parameters

### -param hNotify [in]

Defines the **HANDLE** parameter *hNotify*.

### -param dwColor

Defines the **DWORD** parameter *dwColor*.

### -param fdwFlags

Defines the **DWORD** parameter *fdwFlags*.

### -param pdwResult [out]

Defines the **PDWORD** parameter *pdwResult*.

### -param pPrinterNotifyInfo [in]

Defines the **PVOID** parameter *pPrinterNotifyInfo*.

## -returns

Returns a **BOOL** value.
