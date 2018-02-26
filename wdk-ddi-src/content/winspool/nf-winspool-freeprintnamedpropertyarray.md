---
UID: NF:winspool.FreePrintNamedPropertyArray
title: FreePrintNamedPropertyArray function
author: windows-driver-content
description: "."
old-location: print\freeprintnamedpropertyarray.htm
old-project: print
ms.assetid: 18E24562-F57A-492F-9254-722ABA0B2BC4
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , A, F, FreePrintNamedPropertyArray, FreePrintNamedPropertyArray function [Print Devices], N, P, a, d, e, i, m, n, o, p, print.freeprintnamedpropertyarray, r, t, winspool/FreePrintNamedPropertyArray, y"
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
-	FreePrintNamedPropertyArray
product: Windows
targetos: Windows
req.typenames: BIDI_TYPE
req.product: Windows 10 or later.
---

# FreePrintNamedPropertyArray function


## -description





## -syntax


````
void WINAPI FreePrintNamedPropertyArray(
  _In_        DWORD               cProperties,
  _Inout_opt_ PrintNamedProperty  **ppProperties
);
````


## -parameters




### -param cProperties [in]


### -param ppProperties [in, out, optional]


## -returns



This function does not return a value.



