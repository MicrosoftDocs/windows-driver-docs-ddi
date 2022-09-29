---
UID: NF:winsplp.SpoolerRefreshPrinterChangeNotification
title: SpoolerRefreshPrinterChangeNotification function (winsplp.h)
description: Describes the SpoolerRefreshPrinterChangeNotification function.
tech.root: print
ms.date: 07/27/2022
keywords: ["SpoolerRefreshPrinterChangeNotification function"]
ms.keywords: SpoolerRefreshPrinterChangeNotification, SpoolerRefreshPrinterChangeNotification function [Print Devices], print.spoolerrefreshprinterchangenotification, winsplp/SpoolerRefreshPrinterChangeNotification
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
 - SpoolerRefreshPrinterChangeNotification
 - winsplp/SpoolerRefreshPrinterChangeNotification
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Winsplp.h
api_name:
 - SpoolerRefreshPrinterChangeNotification
---

## -description

Describes the **SpoolerRefreshPrinterChangeNotification** function.

## -parameters

### -param hPrinter [in]

Defines the **HANDLE** parameter *hPrinter*.

### -param dwColor [in]

Defines the **DWORD** parameter *dwColor*.

### -param pOptions [in]

Defines the **PPRINTER_NOTIFY_OPTIONS** parameter *pOptions*.

### -param ppInfo [in, out, optional]

Defines the **PPRINTER_NOTIFY_INFO** parameter *ppInfo*.

## -returns

Returns a **BOOL** value.
