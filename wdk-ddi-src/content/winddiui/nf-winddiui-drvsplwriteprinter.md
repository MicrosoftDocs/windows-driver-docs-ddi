---
UID: NF:winddiui.DrvSplWritePrinter
title: DrvSplWritePrinter function
author: windows-driver-content
description: .
old-location: print\drvsplwriteprinter.htm
old-project: print
ms.assetid: c42bb90a-3c38-4c0c-b523-10e740a027c4
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: DrvSplWritePrinter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winddiui.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DrvSplWritePrinter
req.alt-loc: winddiui.h
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
req.typenames: WINBIO_VERSION, *PWINBIO_VERSION
req.product: Windows 10 or later.
---

# DrvSplWritePrinter function



## -description




## -syntax

````
BOOL WINAPI DrvSplWritePrinter(
   HANDLE  hDriver,
   LPVOID  pBuf,
   DWORD   cbBuf,
   LPDWORD pcWritten
);
````


## -parameters

### -param hDriver 


### -param pBuf 


### -param cbBuf 


### -param pcWritten 


## -remarks
