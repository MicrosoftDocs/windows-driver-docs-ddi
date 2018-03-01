---
UID: NF:winsplp.DevQueryPrint
title: DevQueryPrint function
author: windows-driver-content
description: "."
old-location: print\devqueryprint.htm
old-project: print
ms.assetid: B3135A43-A328-4103-AB75-A37F02322F70
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DevQueryPrint, DevQueryPrint function [Print Devices], print.devqueryprint, winsplp/DevQueryPrint
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Winsplp.h
api_name:
-	DevQueryPrint
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# DevQueryPrint function


## -description





## -syntax


````
BOOL WINAPI DevQueryPrint(
  _In_  HANDLE    hPrinter,
  _In_  LPDEVMODE pDevMode,
  _Out_ DWORD     *pResID
);
````


## -parameters




### -param hPrinter [in]


### -param pDevMode [in]


### -param pResID [out]

