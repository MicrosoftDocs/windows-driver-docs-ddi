---
UID: NC:trustedruntimeclx.PFN_TRSECUREDEVICELOGMESSAGE
title: PFN_TRSECUREDEVICELOGMESSAGE (trustedruntimeclx.h)
description: 
ms.date: 11/20/2020
keywords: ["*PFN_TRSECUREDEVICELOGMESSAGE callback function"]
req.header: trustedruntimeclx.h
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
tech.root: treedrv
f1_keywords:
 - PFN_TRSECUREDEVICELOGMESSAGE
 - trustedruntimeclx/PFN_TRSECUREDEVICELOGMESSAGE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - trustedruntimeclx.h
api_name:
 - PFN_TRSECUREDEVICELOGMESSAGE
---

# *PFN_TRSECUREDEVICELOGMESSAGE callback function

## -description

## -parameters

### -param BindContext

### -param Device

### -param Severity

### -param Message

### -param Arguments

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS values error code. For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -syntax

```cpp
//Declaration

*PFN_TRSECUREDEVICELOGMESSAGE *PfnTrsecuredevicelogmessage;

// Definition

NTSTATUS *PfnTrsecuredevicelogmessage
(
    WDFOBJECT BindContext
    WDFDEVICE Device
    ULONG Severity
    PCSTR Message
    va_list Arguments
)
{...}

```

## -remarks

## -see-also
