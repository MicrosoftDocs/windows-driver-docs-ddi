---
UID: NF:printoem.OEMOutputCharStr
title: OEMOutputCharStr function
author: windows-driver-content
description: OEMOutputCharStr function
old-location: print\oemoutputcharstr.htm
old-project: print
ms.assetid: ac23ec89-b455-4bfd-93a5-2294d8b8ffc2
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: printoem/OEMOutputCharStr, print.oemoutputcharstr, print_obsoletefunctions_250a623a-d7ce-48ba-9163-c24f52eb687d.xml, OEMOutputCharStr function [Print Devices], OEMOutputCharStr
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
-	OEMOutputCharStr
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMOutputCharStr function


## -description




## -syntax


````
VOID APIENTRY OEMOutputCharStr(
       PDEVOBJ                pdevobj,
       PUNIFONTOBJ            pUFObj,
       DWORD                  dwType,
       DWORD                  dwCount,
  _In_ _reads_(dwCount) PVOID pGlyph
);
````


## -parameters




### -param pdevobj


### -param pUFObj


### -param dwType


### -param dwCount


### -param pGlyph [in]


## -returns



This function does not return a value.

<h2><a id="ddk_oemoutputcharstr_gg"></a><a id="DDK_OEMOUTPUTCHARSTR_GG"></a></h2>
This function is obsolete for Windows XP and later. It is supported only for earlier Unidrv plug-ins. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff554267">IPrintOemUni::OutputCharStr</a>.



