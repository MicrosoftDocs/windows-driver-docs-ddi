---
UID: NC:trustedruntimeclx.PFN_TRSECUREDEVICECALLOSSSERVICE
title: PFN_TRSECUREDEVICECALLOSSSERVICE (trustedruntimeclx.h)
description: "Learn more about: *PFN_TRSECUREDEVICECALLOSSSERVICE callback function"
ms.date: 11/20/2020
keywords: ["*PFN_TRSECUREDEVICECALLOSSSERVICE callback function"]
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
 - PFN_TRSECUREDEVICECALLOSSSERVICE
 - trustedruntimeclx/PFN_TRSECUREDEVICECALLOSSSERVICE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - trustedruntimeclx.h
api_name:
 - PFN_TRSECUREDEVICECALLOSSSERVICE
---

# *PFN_TRSECUREDEVICECALLOSSSERVICE callback function

## -description

## -parameters

### -param BindContext

### -param Device

### -param OSServiceGuid

### -param CallData

### -param BytesWritten

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS values error code. For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -syntax

```cpp
//Declaration

*PFN_TRSECUREDEVICECALLOSSSERVICE *PfnTrsecuredevicecallossservice;

// Definition

NTSTATUS *PfnTrsecuredevicecallossservice
(
    WDFOBJECT BindContext
    WDFDEVICE Device
    LPCGUID OSServiceGuid
    PTR_SERVICE_REQUEST CallData
    ULONG_PTR *BytesWritten
)
{...}

```

## -remarks

## -see-also
