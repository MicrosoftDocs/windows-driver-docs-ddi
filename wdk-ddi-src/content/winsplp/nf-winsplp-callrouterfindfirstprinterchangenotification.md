---
UID: NF:winsplp.CallRouterFindFirstPrinterChangeNotification
title: CallRouterFindFirstPrinterChangeNotification function
author: windows-driver-content
description: .
old-location: print\callrouterfindfirstprinterchangenotification.htm
old-project: print
ms.assetid: 7B974255-2FCB-4EFE-B33F-9856E0A09FC4
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: CallRouterFindFirstPrinterChangeNotification
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
req.alt-api: CallRouterFindFirstPrinterChangeNotification
req.alt-loc: Winsplp.h
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
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# CallRouterFindFirstPrinterChangeNotification function



## -description




## -syntax

````
DWORD WINAPI CallRouterFindFirstPrinterChangeNotification(
  _In_ HANDLE                  hPrinterRPC,
       DWORD                   fdwFilterFlags,
       DWORD                   fdwOptions,
  _In_ HANDLE                  hNotify,
  _In_ PPRINTER_NOTIFY_OPTIONS pPrinterNotifyOptions
);
````


## -parameters

### -param hPrinterRPC [in]


### -param fdwFilterFlags 


### -param fdwOptions 


### -param hNotify [in]


### -param pPrinterNotifyOptions [in]


## -remarks
