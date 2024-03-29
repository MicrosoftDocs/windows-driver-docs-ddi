---
UID: NF:winsplp.CallRouterFindFirstPrinterChangeNotification
title: CallRouterFindFirstPrinterChangeNotification function (winsplp.h)
description: Describes the CallRouterFindFirstPrinterChangeNotification function.
tech.root: print
ms.date: 07/29/2022
keywords: ["CallRouterFindFirstPrinterChangeNotification function"]
ms.keywords: CallRouterFindFirstPrinterChangeNotification, CallRouterFindFirstPrinterChangeNotification function [Print Devices], print.callrouterfindfirstprinterchangenotification, winsplp/CallRouterFindFirstPrinterChangeNotification
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
 - CallRouterFindFirstPrinterChangeNotification
 - winsplp/CallRouterFindFirstPrinterChangeNotification
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Winsplp.h
api_name:
 - CallRouterFindFirstPrinterChangeNotification
---

## -description

Describes the **CallRouterFindFirstPrinterChangeNotification** function.

## -parameters

### -param hPrinterRPC [in]

Defines the **HANDLE** parameter *hPrinterRPC*.

### -param fdwFilterFlags

Defines the **DWORD** parameter *fdwFilterFlags*.

### -param fdwOptions

Defines the **DWORD** parameter *fdwOptions*.

### -param hNotify [in]

Defines the **HANDLE** parameter *hNotify*.

### -param pPrinterNotifyOptions [in]

Defines the **PPRINTER_NOTIFY_OPTIONS** parameter *pPrinterNotifyOptions*.

## -returns

Returns a **DWORD** value.
