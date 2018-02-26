---
UID: NF:winspool.GetPrintOutputInfo
title: GetPrintOutputInfo function
author: windows-driver-content
description: "."
old-location: print\getprintoutputinfo.htm
old-project: print
ms.assetid: 0EC09215-48B1-4B71-9B4C-99A25C35269F
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , G, GetPrintOutputInfo, GetPrintOutputInfo function [Print Devices], I, O, P, e, f, i, n, o, p, print.getprintoutputinfo, r, t, u, winspool/GetPrintOutputInfo"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winspool.h
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
-	Winspool.h
apiname:
-	GetPrintOutputInfo
product: Windows
targetos: Windows
req.typenames: BIDI_TYPE
req.product: Windows 10 or later.
---

# GetPrintOutputInfo function


## -description





## -syntax


````
HRESULT WINAPI GetPrintOutputInfo(
  _In_  HWND    hWnd,
  _In_  PCWSTR  pszPrinter,
  _Out_ HANDLE  *phFile,
  _Out_ PWSTR   *ppszOutputFile
);
````


## -parameters




### -param hWnd [in]


### -param pszPrinter [in]


### -param phFile [out]


### -param ppszOutputFile [out]


## -returns



If this function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



