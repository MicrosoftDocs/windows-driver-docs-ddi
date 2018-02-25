---
UID: NF:winsplp.SpoolerRefreshPrinterChangeNotification
title: SpoolerRefreshPrinterChangeNotification function
author: windows-driver-content
description: "."
old-location: print\spoolerrefreshprinterchangenotification.htm
old-project: print
ms.assetid: 86D8D605-3620-4F43-B4A5-6AF568265E92
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , C, N, P, R, S, SpoolerRefreshPrinterChangeNotification, SpoolerRefreshPrinterChangeNotification function [Print Devices], a, c, e, f, g, h, i, l, n, o, p, print.spoolerrefreshprinterchangenotification, r, s, t, winsplp/SpoolerRefreshPrinterChangeNotification"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Winsplp.h
apiname:
-	SpoolerRefreshPrinterChangeNotification
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# SpoolerRefreshPrinterChangeNotification function


## -description





## -syntax


````
BOOL WINAPI SpoolerRefreshPrinterChangeNotification(
  _In_        HANDLE                    hPrinter,
  _In_        DWORD                     dwColor,
  _In_        PPRINTER_NOTIFY_OPTIONS   pOptions,
  _Inout_opt_ PPRINTER_NOTIFY_INFO      ppInfo
);
````


## -parameters




### -param hPrinter [in]


### -param dwColor [in]


### -param pOptions [in]


### -param ppInfo [in, out, optional]

