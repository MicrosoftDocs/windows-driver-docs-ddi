---
UID: NF:winsplp.ReplyPrinterChangeNotificationEx
title: ReplyPrinterChangeNotificationEx function
author: windows-driver-content
description: "."
old-location: print\replyprinterchangenotificationex.htm
old-project: print
ms.assetid: A3A906C0-FA96-4008-B904-1DA333B59833
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: ReplyPrinterChangeNotificationEx, winsplp/ReplyPrinterChangeNotificationEx, print.replyprinterchangenotificationex, ReplyPrinterChangeNotificationEx function [Print Devices]
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
-	ReplyPrinterChangeNotificationEx
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# ReplyPrinterChangeNotificationEx function


## -description





## -syntax


````
 WINAPI ReplyPrinterChangeNotificationEx(
  _In_  HANDLE    hNotify,
        DWORD     dwColor,
        DWORD     fdwFlags,
  _Out_ PDWORD    pdwResult,
  _In_  PVOID     pPrinterNotifyInfo
);
````


## -parameters




### -param hNotify [in]


### -param dwColor


### -param fdwFlags


### -param pdwResult [out]


### -param pPrinterNotifyInfo [in]

