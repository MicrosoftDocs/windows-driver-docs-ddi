---
UID: NC:trustedruntimeclx.PFN_TRSECUREDEVICECOMPLETEASYNCREQUEST
title: PFN_TRSECUREDEVICECOMPLETEASYNCREQUEST (trustedruntimeclx.h)
description: 
ms.assetid: ec151fa2-ab0d-4858-8e4d-8201b80cd138
ms.date: 10/19/2018
keywords: ["*PFN_TRSECUREDEVICECOMPLETEASYNCREQUEST callback function"]
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
f1_keywords:
 - PFN_TRSECUREDEVICECOMPLETEASYNCREQUEST
 - trustedruntimeclx/PFN_TRSECUREDEVICECOMPLETEASYNCREQUEST
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - trustedruntimeclx.h
api_name:
 - PFN_TRSECUREDEVICECOMPLETEASYNCREQUEST
---

# *PFN_TRSECUREDEVICECOMPLETEASYNCREQUEST callback function


## -description

## -parameters

### -param BindContext: 

### -param RequestHandle: 

### -param Result: 

### -param BytesWritten: 

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values).

## -syntax

```cpp
//Declaration

*PFN_TRSECUREDEVICECOMPLETEASYNCREQUEST *PfnTrsecuredevicecompleteasyncrequest; 

// Definition

NTSTATUS *PfnTrsecuredevicecompleteasyncrequest 
(
	WDFOBJECT BindContext
	PVOID RequestHandle
	NTSTATUS Result
	ULONG_PTR BytesWritten
)
{...}

```

## -remarks

## -see-also

