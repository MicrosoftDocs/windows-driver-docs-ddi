---
UID: NC:mbbcx.PFN_MBBDEVICEINITCONFIG
title: PFN_MBBDEVICEINITCONFIG
author: windows-driver-content
description: 
ms.assetid: 0084e95e-6dea-45b9-a024-3300579967e1
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
-	PFN_MBBDEVICEINITCONFIG
product: Windows
targetos: Windows
---

# PFN_MBBDEVICEINITCONFIG callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFN_MBBDEVICEINITCONFIG PfnMbbdeviceinitconfig; 

// Definition

WDFAPI PfnMbbdeviceinitconfig 
(
	PMBB_DRIVER_GLOBALS DriverGlobals
	PWDFDEVICE_INIT DeviceInit
)
{...}

```

## -parameters

### -param DriverGlobals: 
### -param DeviceInit: 



## -returns

Returns WDFAPI that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also