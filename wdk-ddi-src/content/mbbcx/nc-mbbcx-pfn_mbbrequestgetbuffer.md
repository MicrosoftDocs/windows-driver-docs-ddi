---
UID: NC:mbbcx.PFN_MBBREQUESTGETBUFFER
title: PFN_MBBREQUESTGETBUFFER
author: windows-driver-content
description: 
ms.assetid: 06b68d04-36fc-4699-b761-7d231b88a217
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
-	PFN_MBBREQUESTGETBUFFER
product: Windows
targetos: Windows
---

# PFN_MBBREQUESTGETBUFFER callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFN_MBBREQUESTGETBUFFER PfnMbbrequestgetbuffer; 

// Definition

WDFAPI PfnMbbrequestgetbuffer 
(
	PMBB_DRIVER_GLOBALS DriverGlobals
	MBBREQUEST Request
	size_t *BufferSize
)
{...}

```

## -parameters

### -param DriverGlobals: 
### -param Request: 
### -param *BufferSize: 



## -returns

Returns WDFAPI that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also