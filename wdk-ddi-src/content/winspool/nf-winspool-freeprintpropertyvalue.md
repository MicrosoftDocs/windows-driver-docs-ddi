---
UID: NF:winspool.FreePrintPropertyValue
title: FreePrintPropertyValue function (winspool.h)
description: Frees the value that is retrieved using GetJobNamedPropertyValue function.
old-location: print\freeprintpropertyvalue.htm
tech.root: print
ms.date: 11/18/2019
keywords: ["FreePrintPropertyValue function"]
ms.keywords: FreePrintPropertyValue, FreePrintPropertyValue function [Print Devices], print.freeprintpropertyvalue, winspool/FreePrintPropertyValue
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
targetos: Windows
req.typenames: 
f1_keywords:
 - FreePrintPropertyValue
 - winspool/FreePrintPropertyValue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - spoolss.dll
 - WinSpool.drv
api_name:
 - FreePrintPropertyValue
---

# FreePrintPropertyValue function


## -description

Frees the value that is retrieved using the [GetJobNamedPropertyValue](./nf-winspool-getjobnamedpropertyvalue.md) function.

## -parameters

### -param pValue 

[in, out]
Pointer to **PrintPropertyValue** structure that is returned from [GetJobNamedPropertyValue](./nf-winspool-getjobnamedpropertyvalue.md).
