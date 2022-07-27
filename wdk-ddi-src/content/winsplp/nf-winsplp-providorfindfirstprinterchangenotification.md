---
UID: NF:winsplp.ProvidorFindFirstPrinterChangeNotification
title: ProvidorFindFirstPrinterChangeNotification function (winsplp.h)
description: Describes the ProvidorFindFirstPrinterChangeNotification function.
tech.root: print
ms.date: 07/27/2022
keywords: ["ProvidorFindFirstPrinterChangeNotification function"]
ms.keywords: ProvidorFindFirstPrinterChangeNotification, ProvidorFindFirstPrinterChangeNotification function [Print Devices], print.providorfindfirstprinterchangenotification, winsplp/ProvidorFindFirstPrinterChangeNotification
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
 - ProvidorFindFirstPrinterChangeNotification
 - winsplp/ProvidorFindFirstPrinterChangeNotification
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Winsplp.h
api_name:
 - ProvidorFindFirstPrinterChangeNotification
---

## -description

Describes the **ProvidorFindFirstPrinterChangeNotification** function.

## -parameters

### -param hPrinter [in]

Defines the **HANDLE** parameter *hPrinter*.

### -param fdwFlags

Defines the **DWORD** parameter *fdwFlags*.

### -param fdwOptions

Defines the **DWORD** parameter *fdwOptions*.

### -param hNotify [in]

Defines the **HANDLE** parameter *hNotify*.

### -param pPrinterNotifyOptions [in, optional]

Defines the **PVOID** parameter *pPrinterNotifyOptions*.

### -param pvReserved1 [out, optional]

Defines the **PVOID** parameter *pvReserved1*.

## -returns

Returns a **BOOL** value.
