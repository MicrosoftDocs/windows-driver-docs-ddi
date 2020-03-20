---
UID: NF:dispmprt.DlSynchronizeExecution
title: DlSynchronizeExecution function
author: windows-driver-content
description: Synchronizes the execution of a miniport driver-supplied DXGKCB_SYNCHRONIZE_EXECUTION function with the miniport driver's DxgkDdiInterruptRoutine function.
tech.root: display
ms.assetid: e7eb6f58-dbf7-47ab-85f1-72d6aba64a09
ms.author: windowsdriverdev
ms.date: 04/04/2019 
keywords: ["DlSynchronizeExecution function"]
f1_keywords:
 - "dispmprt/DlSynchronizeExecution"
ms.keywords: DlSynchronizeExecution
req.header: dispmprt.h
req.include-header:
req.target-type:
req.target-min-winverclnt: 
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- DllExport
api_location: 
- Displib.lib
- Displib.dll
api_name: 
- DlSynchronizeExecution
product: 
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# DlSynchronizeExecution function


## -description

Synchronizes the execution of a miniport driver-supplied [DXGKCB_SYNCHRONIZE_EXECUTION](nc-dispmprt-dxgkcb_synchronize_execution.md) function with the miniport driver's DxgkDdiInterruptRoutine function.

## -parameters

### -param DeviceHandle

A handle that represents a display adapter.

### -param Priority



### -param SynchronizeRoutine



### -param Context



### -param MessageNumber




## -returns

This function returns BOOLEAN.

## -remarks

## -see-also
