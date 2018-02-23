---
UID: NF:printoem.OEMDisablePDEV
title: OEMDisablePDEV function
author: windows-driver-content
description: OEMDisablePDEV function
old-location: print\oemdisablepdev.htm
old-project: print
ms.assetid: a58d333f-f092-4f7a-b6ae-ebba4f894678
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: print_obsoletefunctions_d0b9c4d2-19f5-4702-a99d-5549ae1b5b3d.xml, printoem/OEMDisablePDEV, OEMDisablePDEV function [Print Devices], OEMDisablePDEV, print.oemdisablepdev
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
-	printoem.h
apiname:
-	OEMDisablePDEV
product: Windows
targetos: Windows
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

<h2><a id="ddk_oemdisablepdev_gg"></a><a id="DDK_OEMDISABLEPDEV_GG"></a></h2>
This function is obsolete for Windows XP and later. It is supported only for earlier plug-ins. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff553209">IPrintOemPS::DisablePDEV</a> (Pscript) or <a href="https://msdn.microsoft.com/library/windows/hardware/ff554238">IPrintOemUni::DisablePDEV</a> (Unidrv).



