---
UID: NC:trustedruntimeclx.PFN_TRSECUREDEVICECALLOSSSERVICE
title: *PFN_TRSECUREDEVICECALLOSSSERVICE
author: windows-driver-content
description: 
ms.assetid: 66deec39-5ce0-4f88-8420-a2845e0f4c00
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
-	*PFN_TRSECUREDEVICECALLOSSSERVICE
product: Windows
targetos: Windows
---

# *PFN_TRSECUREDEVICECALLOSSSERVICE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
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

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also