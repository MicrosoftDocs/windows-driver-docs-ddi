---
UID: NC:trustedruntimeclx.PFN_TRSECUREDEVICECALLOSSSERVICE
title: PFN_TRSECUREDEVICECALLOSSSERVICE (trustedruntimeclx.h)
description: 
ms.assetid: 66deec39-5ce0-4f88-8420-a2845e0f4c00
ms.date: 10/19/2018
f1_keywords:
 - "trustedruntimeclx/*PFN_TRSECUREDEVICECALLOSSSERVICE"
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
- apiref
api_type: 
- UserDefined
api_location: 
- trustedruntimeclx.h
api_name: 
- PFN_TRSECUREDEVICECALLOSSSERVICE
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# *PFN_TRSECUREDEVICECALLOSSSERVICE callback function

## -description

 

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

## -parameters

### -param BindContext: 
### -param Device: 
### -param OSServiceGuid: 
### -param CallData: 
### -param *BytesWritten: 



## -returns


Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks




## -see-also
