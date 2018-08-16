---
UID: NC:trustedruntimeclx.PFN_TRSECUREDEVICEQUERYOSSERVICE
title: *PFN_TRSECUREDEVICEQUERYOSSERVICE
author: windows-driver-content
description: 
ms.assetid: 28894ef9-7e17-4955-a4c9-6297d1f9fb30
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
-	*PFN_TRSECUREDEVICEQUERYOSSERVICE
product:
-	Windows
targetos: Windows
---

# *PFN_TRSECUREDEVICEQUERYOSSERVICE callback function

## -description

 

## -prototype

```
//Declaration

*PFN_TRSECUREDEVICEQUERYOSSERVICE *PfnTrsecuredevicequeryosservice; 

// Definition

NTSTATUS *PfnTrsecuredevicequeryosservice 
(
	WDFOBJECT BindContext
	WDFDEVICE Device
	LPCGUID OSServiceGuid
	PTR_SERVICE_INFORMATION Information
)
{...}

```

## -parameters

### -param BindContext: 
### -param Device: 
### -param OSServiceGuid: 
### -param Information: 



## -returns


Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks




## -see-also