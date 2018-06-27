---
UID: NC:mbbcx.PFN_MBBADAPTERINITIALIZE
title: PFN_MBBADAPTERINITIALIZE
author: windows-driver-content
description: 
ms.assetid: cb04c8a9-5cd5-46a3-a63a-e7faeb9f5f0a
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
-	PFN_MBBADAPTERINITIALIZE
product: Windows
targetos: Windows
---

# PFN_MBBADAPTERINITIALIZE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFN_MBBADAPTERINITIALIZE PfnMbbadapterinitialize; 

// Definition

WDFAPI PfnMbbadapterinitialize 
(
	PMBB_DRIVER_GLOBALS DriverGlobals
	NETADAPTER Adapter
)
{...}

```

## -parameters

### -param DriverGlobals: 
### -param Adapter: 



## -returns

Returns WDFAPI that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also