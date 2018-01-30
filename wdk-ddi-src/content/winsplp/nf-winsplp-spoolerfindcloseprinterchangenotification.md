---
UID: NF:winsplp.SpoolerFindClosePrinterChangeNotification
title: SpoolerFindClosePrinterChangeNotification function
author: windows-driver-content
description: "."
old-location: print\spoolerfindcloseprinterchangenotification.htm
old-project: print
ms.assetid: 13C65DAB-04BA-4B19-B810-B484F7C1C4DA
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: SpoolerFindClosePrinterChangeNotification function [Print Devices], SpoolerFindClosePrinterChangeNotification, winsplp/SpoolerFindClosePrinterChangeNotification, print.spoolerfindcloseprinterchangenotification
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
-	SpoolerFindClosePrinterChangeNotification
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# SpoolerFindClosePrinterChangeNotification function


## -description





## -syntax


````
BOOL WINAPI SpoolerFindClosePrinterChangeNotification(
  _In_ HANDLE                   hPrinter
);
````


## -parameters




### -param hPrinter [in]


