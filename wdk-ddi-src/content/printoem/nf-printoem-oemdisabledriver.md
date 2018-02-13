---
UID: NF:printoem.OEMDisableDriver
title: OEMDisableDriver function
author: windows-driver-content
description: OEMDisableDriver function
old-location: print\oemdisabledriver.htm
old-project: print
ms.assetid: 9b48e2c0-bd44-49ed-83e8-1e4895858e9b
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: print.oemdisabledriver, print_obsoletefunctions_b9594259-f9e5-43bf-b2dd-18ace2ddc25c.xml, OEMDisableDriver function [Print Devices], OEMDisableDriver, printoem/OEMDisableDriver
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
-	OEMDisableDriver
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMDisableDriver function


## -description




## -syntax


````
VOID APIENTRY OEMDisableDriver(
   VOID 
);
````


## -parameters






## -returns



This function does not return a value.

<h2><a id="ddk_oemdisabledriver_gg"></a><a id="DDK_OEMDISABLEDRIVER_GG"></a></h2>
This function is obsolete for Windows XP and later. It is supported only for earlier plug-ins. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff553207">IPrintOemPS::DisableDriver</a> (Pscript) or <a href="https://msdn.microsoft.com/library/windows/hardware/ff554232">IPrintOemUni::DisableDriver</a> (Unidrv).



