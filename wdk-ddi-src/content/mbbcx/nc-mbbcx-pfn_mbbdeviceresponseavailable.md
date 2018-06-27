---
UID: NC:mbbcx.PFN_MBBDEVICERESPONSEAVAILABLE
title: PFN_MBBDEVICERESPONSEAVAILABLE
author: windows-driver-content
description: 
ms.assetid: 6b987bf7-ea64-4bb3-b255-c89fbf67ca13
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
-	PFN_MBBDEVICERESPONSEAVAILABLE
product: Windows
targetos: Windows
---

# PFN_MBBDEVICERESPONSEAVAILABLE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFN_MBBDEVICERESPONSEAVAILABLE PfnMbbdeviceresponseavailable; 

// Definition

WDFAPI PfnMbbdeviceresponseavailable 
(
	PMBB_DRIVER_GLOBALS DriverGlobals
	WDFDEVICE Device
)
{...}

```

## -parameters

### -param DriverGlobals: 
### -param Device: 



## -returns

Returns WDFAPI that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also