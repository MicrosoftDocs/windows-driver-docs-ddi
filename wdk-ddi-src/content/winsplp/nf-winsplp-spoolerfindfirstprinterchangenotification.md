---
UID: NF:winsplp.SpoolerFindFirstPrinterChangeNotification
title: SpoolerFindFirstPrinterChangeNotification function (winsplp.h)
description: Describes the SpoolerFindFirstPrinterChangeNotification function.
tech.root: print
ms.date: 07/27/2022
keywords: ["SpoolerFindFirstPrinterChangeNotification function"]
ms.keywords: SpoolerFindFirstPrinterChangeNotification, SpoolerFindFirstPrinterChangeNotification function [Print Devices], print.spoolerfindfirstprinterchangenotification, winsplp/SpoolerFindFirstPrinterChangeNotification
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
 - SpoolerFindFirstPrinterChangeNotification
 - winsplp/SpoolerFindFirstPrinterChangeNotification
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Winsplp.h
api_name:
 - SpoolerFindFirstPrinterChangeNotification
---

## -description

Describes the **SpoolerFindFirstPrinterChangeNotification** function.

## -parameters

### -param hPrinter [in]

Defines the **HANDLE** parameter *hPrinter*.

### -param fdwFilterFlags

Defines the **DWORD** parameter *fdwFilterFlags*.

### -param fdwOptions

Defines the **DWORD** parameter *fdwOptions*.

### -param pPrinterNotifyOptions [in]

Defines the **PVOID** parameter *pPrinterNotifyOptions*.

### -param pvReserved [in, optional]

Defines the **PVOID** parameter *pvReserved*.

### -param pNotificationConfig [in]

Defines the **PVOID** parameter *pNotificationConfig*.

### -param phNotify [out, optional]

Defines the **PHANDLE** parameter *phNotify*.

### -param phEvent [out, optional]

Defines the **PHANDLE** parameter *phEvent*.

## -returns

Returns a **BOOL** value.
