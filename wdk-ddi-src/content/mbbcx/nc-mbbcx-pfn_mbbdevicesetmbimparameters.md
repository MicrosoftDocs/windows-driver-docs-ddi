---
UID: NC:mbbcx.PFN_MBBDEVICESETMBIMPARAMETERS
title: PFN_MBBDEVICESETMBIMPARAMETERS
author: windows-driver-content
description: 
ms.assetid: e9067aa9-3026-4baf-aa17-613907f6b04a
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: mbbcx.h
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
-	mbbcx.h
api_name: 
-	PFN_MBBDEVICESETMBIMPARAMETERS
product: Windows
targetos: Windows
---

# PFN_MBBDEVICESETMBIMPARAMETERS callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFN_MBBDEVICESETMBIMPARAMETERS PfnMbbdevicesetmbimparameters; 

// Definition

WDFAPI PfnMbbdevicesetmbimparameters 
(
	PMBB_DRIVER_GLOBALS DriverGlobals
	WDFDEVICE Device
	PMBB_DEVICE_MBIM_PARAMETERS MbimParameters
)
{...}

```

## -parameters

### -param DriverGlobals: 
### -param Device: 
### -param MbimParameters: 



## -returns

Returns WDFAPI that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also