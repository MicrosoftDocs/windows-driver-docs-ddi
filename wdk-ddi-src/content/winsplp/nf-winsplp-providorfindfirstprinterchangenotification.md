---
UID: NF:winsplp.ProvidorFindFirstPrinterChangeNotification
title: ProvidorFindFirstPrinterChangeNotification function
author: windows-driver-content
description: "."
old-location: print\providorfindfirstprinterchangenotification.htm
old-project: print
ms.assetid: AFDA244D-D692-44C1-8BA3-5E1F013558D6
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: winsplp/ProvidorFindFirstPrinterChangeNotification, ProvidorFindFirstPrinterChangeNotification, ProvidorFindFirstPrinterChangeNotification function [Print Devices], print.providorfindfirstprinterchangenotification
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
-	ProvidorFindFirstPrinterChangeNotification
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# ProvidorFindFirstPrinterChangeNotification function


## -description





## -syntax


````
BOOL WINAPI ProvidorFindFirstPrinterChangeNotification(
  _In_      HANDLE                   hPrinter,
            DWORD                    fdwFlags,
            DWORD                    fdwOptions,
  _In_      HANDLE                   hNotify,
  _In_opt_  PVOID                    pPrinterNotifyOptions,
  _Out_opt_ PVOID                    pvReserved1
);
````


## -parameters




### -param hPrinter [in]


### -param fdwFlags


### -param fdwOptions


### -param hNotify [in]


### -param pPrinterNotifyOptions [in, optional]


### -param pvReserved1 [out, optional]

