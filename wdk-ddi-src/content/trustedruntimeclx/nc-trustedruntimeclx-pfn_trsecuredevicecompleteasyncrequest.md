---
UID: NC:trustedruntimeclx.PFN_TRSECUREDEVICECOMPLETEASYNCREQUEST
title: *PFN_TRSECUREDEVICECOMPLETEASYNCREQUEST
author: windows-driver-content
description: 
ms.assetid: ec151fa2-ab0d-4858-8e4d-8201b80cd138
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	trustedruntimeclx.h
api_name: 
-	*PFN_TRSECUREDEVICECOMPLETEASYNCREQUEST
product:
-	Windows
targetos: Windows
---

# *PFN_TRSECUREDEVICECOMPLETEASYNCREQUEST callback function

## -description

 

## -prototype

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

## -parameters

### -param BindContext: 
### -param RequestHandle: 
### -param Result: 
### -param BytesWritten: 



## -returns


Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks




## -see-also
