---
UID: NF:winspool.FreePrintPropertyValue
title: FreePrintPropertyValue function
author: windows-driver-content
description: Frees the value that is retrieved using GetJobNamedPropertyValue function.
old-location: print\freeprintpropertyvalue.htm
old-project: print
ms.assetid: 38B760D9-CB6E-45AD-A83F-3C26D1B31A30
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , F, FreePrintPropertyValue, FreePrintPropertyValue function [Print Devices], P, V, a, e, i, l, n, o, p, print.freeprintpropertyvalue, r, t, u, winspool/FreePrintPropertyValue, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winspool.h
req.include-header: Winspool.h
req.target-type: Desktop
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
req.lib: WinSpool.lib
req.dll: Spoolss.dll; WinSpool.drv
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	spoolss.dll
-	WinSpool.drv
apiname:
-	FreePrintPropertyValue
product: Windows
targetos: Windows
req.typenames: BIDI_TYPE
req.product: Windows 10 or later.
---

# FreePrintPropertyValue function


## -description


Frees the value that is retrieved using <a href="..\winspool\nf-winspool-getjobnamedpropertyvalue.md">GetJobNamedPropertyValue</a> function. 



## -syntax


````
DWORD WINAPI FreePrintPropertyValue(
  _Inout_ PrintPropertyValue *pValue
);
````


## -parameters




### -param pValue [in, out]

Pointer to <b>PrintPropertyValue</b> structure that is returned from <a href="..\winspool\nf-winspool-getjobnamedpropertyvalue.md">GetJobNamedPropertyValue</a>. 



## -returns



If the operation succeeds, the function returns <b>ERROR_SUCCESS</b>.  




