---
UID: NF:printoem.OEMSendFontCmd
title: OEMSendFontCmd function
author: windows-driver-content
description: OEMSendFontCmd function
old-location: print\oemsendfontcmd.htm
old-project: print
ms.assetid: 4dcc2ec0-6a75-4fc0-800c-c1ce12e3fd6a
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: OEMSendFontCmd
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
req.alt-api: OEMSendFontCmd
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

# OEMSendFontCmd function



## -description

## -syntax

````
VOID APIENTRY OEMSendFontCmd(
   PDEVOBJ      pdevobj,
   PUNIFONTOBJ  pUFObj,
   PFINVOCATION pFInv
);
````


## -parameters

### -param pdevobj 


### -param pUFObj 


### -param pFInv 


## -returns
This function does not return a value.

This function is obsolete for Windows XP and later. It is supported only for earlier Unidrv plug-ins. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff554274">IPrintOemUni::SendFontCmd</a>.


## -remarks
