---
UID: NC:trustedruntimeclx.PFN_TRSECUREDEVICEHANDOFFSERVICEDEVICECONTROL
title: PFN_TRSECUREDEVICEHANDOFFSERVICEDEVICECONTROL
description: 
ms.assetid: 554690bc-e0aa-411a-9168-40ea01012d88
ms.date: 10/19/2018
ms.topic: callback
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
-	PFN_TRSECUREDEVICEHANDOFFSERVICEDEVICECONTROL
product:
-	Windows
targetos: Windows
ms.custom: RS5
---

# PFN_TRSECUREDEVICEHANDOFFSERVICEDEVICECONTROL callback function

## -description

 

## -prototype

```cpp
//Declaration

PFN_TRSECUREDEVICEHANDOFFSERVICEDEVICECONTROL PfnTrsecuredevicehandoffservicedevicecontrol; 

// Definition

WDFAPI PfnTrsecuredevicehandoffservicedevicecontrol 
(
	WDFOBJECT BindContextObject
	PWDFDEVICE_INIT DeviceInit
	LPGUID ServiceGuid
	PTR_SECURE_SERVICE_CALLBACKS Callbacks
	WDFDEVICE *ServiceDevice
)
{...}

```

## -parameters

### -param BindContextObject: 
### -param DeviceInit: 
### -param ServiceGuid: 
### -param Callbacks: 
### -param *ServiceDevice: 



## -returns

Returns WDFAPI.

## -remarks




## -see-also
