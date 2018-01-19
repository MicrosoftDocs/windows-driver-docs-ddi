---
UID: NF:printoem.OEMDisablePDEV
title: OEMDisablePDEV function
author: windows-driver-content
description: OEMDisablePDEV function
old-location: print\oemdisablepdev.htm
old-project: print
ms.assetid: a58d333f-f092-4f7a-b6ae-ebba4f894678
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: OEMDisablePDEV
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: OEMDisablePDEV
req.alt-loc: printoem.h
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
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMDisablePDEV function



## -description

## -syntax

````
VOID APIENTRY OEMDisablePDEV(
   PDEVOBJ pdevobj
);
````


## -parameters

### -param pdevobj 


## -returns
This function does not return a value.

This function is obsolete for Windows XP and later. It is supported only for earlier plug-ins. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff553209">IPrintOemPS::DisablePDEV</a> (Pscript) or <a href="https://msdn.microsoft.com/library/windows/hardware/ff554238">IPrintOemUni::DisablePDEV</a> (Unidrv).


## -remarks
