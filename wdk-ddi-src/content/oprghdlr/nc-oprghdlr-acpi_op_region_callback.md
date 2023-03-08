---
UID: NC:oprghdlr.ACPI_OP_REGION_CALLBACK
title: ACPI_OP_REGION_CALLBACK (oprghdlr.h)
description: Describes the ACPI_OP_REGION_CALLBACK callback function.
ms.date: 03/03/2023
keywords: ["ACPI_OP_REGION_CALLBACK callback function"]
req.header: oprghdlr.h
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
ms.custom: RS5
tech.root: acpi
f1_keywords:
 - ACPI_OP_REGION_CALLBACK
 - oprghdlr/ACPI_OP_REGION_CALLBACK
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - oprghdlr.h
api_name:
 - ACPI_OP_REGION_CALLBACK
product:
 - Windows
---

## -description

## -parameters

### -param Context

Defines the **PVOID** parameter *Context*.

## -syntax

```cpp
//Declaration

ACPI_OP_REGION_CALLBACK AcpiOpRegionCallback;

// Definition

VOID AcpiOpRegionCallback
(
    PVOID Context
)
{...}

```

## -remarks

## -see-also
