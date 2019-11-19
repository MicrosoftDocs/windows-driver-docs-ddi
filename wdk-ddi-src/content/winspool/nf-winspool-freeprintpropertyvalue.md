---
UID: NF:winspool.FreePrintPropertyValue
title: FreePrintPropertyValue function (winspool.h)
description: Frees the value that is retrieved using GetJobNamedPropertyValue function.
old-location: print\freeprintpropertyvalue.htm
tech.root: print
ms.assetid: 38B760D9-CB6E-45AD-A83F-3C26D1B31A30
ms.date: 11/18/2019
ms.keywords: FreePrintPropertyValue, FreePrintPropertyValue function [Print Devices], print.freeprintpropertyvalue, winspool/FreePrintPropertyValue
ms.topic: function
f1_keywords:
 - "winspool/FreePrintPropertyValue"
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# FreePrintPropertyValue function

## -description

Frees the value that is retrieved using the [GetJobNamedPropertyValue](https://docs.microsoft.com/windows-hardware/drivers/ddi/winspool/nf-winspool-getjobnamedpropertyvalue) function.

## -parameters

### -param pValue [in, out]

Pointer to **PrintPropertyValue** structure that is returned from [GetJobNamedPropertyValue](https://docs.microsoft.com/windows-hardware/drivers/ddi/winspool/nf-winspool-getjobnamedpropertyvalue).
