---
UID: NC:trustedruntimeclx.PFN_TRSECUREDEVICEHANDOFFMASTERDEVICECONTROL
title: PFN_TRSECUREDEVICEHANDOFFMASTERDEVICECONTROL
description: 
ms.assetid: ad975985-ee86-4f2d-ad02-16d5818b12a3
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
-	PFN_TRSECUREDEVICEHANDOFFMASTERDEVICECONTROL
product:
-	Windows
targetos: Windows
ms.custom: RS5
---

# PFN_TRSECUREDEVICEHANDOFFMASTERDEVICECONTROL callback function

## -description

 

## -prototype

```cpp
//Declaration

PFN_TRSECUREDEVICEHANDOFFMASTERDEVICECONTROL PfnTrsecuredevicehandoffmasterdevicecontrol; 

// Definition

WDFAPI PfnTrsecuredevicehandoffmasterdevicecontrol 
(
	WDFOBJECT BindContextObject
	PWDFDEVICE_INIT DeviceInit
	PTR_SECURE_DEVICE_CALLBACKS Callbacks
	WDFDEVICE *MasterDevice
)
{...}

```

## -parameters

### -param BindContextObject: 
### -param DeviceInit: 
### -param Callbacks: 
### -param *MasterDevice: 



## -returns

Returns WDFAPI.

## -remarks




## -see-also
