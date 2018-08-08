---
UID: NC:trustedruntimeclx.PFN_TRSECUREDEVICEHANDOFFSERVICEDEVICECONTROL
title: PFN_TRSECUREDEVICEHANDOFFSERVICEDEVICECONTROL
author: windows-driver-content
description: 
ms.assetid: 554690bc-e0aa-411a-9168-40ea01012d88
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
-	PFN_TRSECUREDEVICEHANDOFFSERVICEDEVICECONTROL
product: Windows
targetos: Windows
---

# PFN_TRSECUREDEVICEHANDOFFSERVICEDEVICECONTROL callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
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

Returns WDFAPI that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also