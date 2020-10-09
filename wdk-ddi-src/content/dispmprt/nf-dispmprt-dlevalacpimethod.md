---
UID: NF:dispmprt.DlEvalAcpiMethod
title: DlEvalAcpiMethod function
description: Evaluates a specified ACPI method on a display adapter or on a child device of a display adapter.
tech.root: display
ms.assetid: dc58e082-25c3-45c1-ad62-718ab21a156c
ms.date: 04/04/2019
keywords: ["DlEvalAcpiMethod function"]
ms.keywords: DlEvalAcpiMethod
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
 - DlEvalAcpiMethod
 - dispmprt/DlEvalAcpiMethod
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - Displib.lib
 - Displib.dll
api_name:
 - DlEvalAcpiMethod
product:
 - Windows
dev_langs:
 - c++
---

# DlEvalAcpiMethod function


## -description

Evaluates a specified ACPI method on a display adapter or on a child device of a display adapter.

## -parameters

### -param DeviceHandle

A handle that represents a display adapter.

### -param DeviceUid

The unique identifier for the ACPI device on which the method will be evaluated.

### -param AcpiInputBuffer

The ACPI input buffer.

### -param AcpiInputSize

The ACPI input size.

### -param AcpiOutputBuffer

The ACPI output buffer.

### -param AcpiOutputSize

The ACPI output size.

## -returns

This function returns NTSTATUS.

## -remarks

## -see-also

[DXGKCB_EVAL_ACPI_METHOD](nc-dispmprt-dxgkcb_eval_acpi_method.md) callback function

