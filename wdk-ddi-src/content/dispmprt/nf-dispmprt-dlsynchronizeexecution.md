---
UID: NF:dispmprt.DlSynchronizeExecution
title: DlSynchronizeExecution function
description: Synchronizes the execution of a miniport driver-supplied DXGKCB_SYNCHRONIZE_EXECUTION function with the miniport driver's DxgkDdiInterruptRoutine function.
tech.root: display
ms.date: 04/04/2019
keywords: ["DlSynchronizeExecution function"]
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
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - DlSynchronizeExecution
 - dispmprt/DlSynchronizeExecution
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
dev_langs:
 - c++
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

