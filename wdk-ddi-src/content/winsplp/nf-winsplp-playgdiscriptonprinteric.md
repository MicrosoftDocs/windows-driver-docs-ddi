---
UID: NF:winsplp.PlayGdiScriptOnPrinterIC
title: PlayGdiScriptOnPrinterIC function
author: windows-driver-content
description: "."
old-location: print\playgdiscriptonprinteric.htm
old-project: print
ms.assetid: DB5FCF40-77C2-4741-9E6B-77A9CD98E29A
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: PlayGdiScriptOnPrinterIC, PlayGdiScriptOnPrinterIC function [Print Devices], print.playgdiscriptonprinteric, winsplp/PlayGdiScriptOnPrinterIC
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
-	PlayGdiScriptOnPrinterIC
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# PlayGdiScriptOnPrinterIC function


## -description





## -syntax


````
BOOL WINAPI PlayGdiScriptOnPrinterIC(
  _In_  HANDLE   hPrinterIC,
  _In_  LPBYTE   pIn,
  _In_  DWORD    cIn,
  _Out_ LPBYTE   pOut,
  _In_  DWORD    cOut,
  _In_  DWORD    ul
);
````


## -parameters




### -param hPrinterIC [in]


### -param pIn [in]


### -param cIn [in]


### -param pOut [out]


### -param cOut [in]


### -param ul [in]

