---
UID: NC:mbbcx.PFN_MBBDEVICEINITIALIZE
title: PFN_MBBDEVICEINITIALIZE
author: windows-driver-content
description: 
ms.assetid: dc8f5587-2b4d-4b33-a830-2b49372b0630
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
-	PFN_MBBDEVICEINITIALIZE
product: Windows
targetos: Windows
---

# PFN_MBBDEVICEINITIALIZE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFN_MBBDEVICEINITIALIZE PfnMbbdeviceinitialize; 

// Definition

WDFAPI PfnMbbdeviceinitialize 
(
	PMBB_DRIVER_GLOBALS DriverGlobals
	WDFDEVICE Device
	PMBB_DEVICE_CONFIG Config
)
{...}

```

## -parameters

### -param DriverGlobals: 
### -param Device: 
### -param Config: 



## -returns

Returns WDFAPI that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also