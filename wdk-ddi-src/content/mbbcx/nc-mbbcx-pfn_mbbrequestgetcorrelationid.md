---
UID: NC:mbbcx.PFN_MBBREQUESTGETCORRELATIONID
title: PFN_MBBREQUESTGETCORRELATIONID
author: windows-driver-content
description: 
ms.assetid: dd2cca81-92c1-4833-a33d-59b14273773e
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
-	PFN_MBBREQUESTGETCORRELATIONID
product: Windows
targetos: Windows
---

# PFN_MBBREQUESTGETCORRELATIONID callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFN_MBBREQUESTGETCORRELATIONID PfnMbbrequestgetcorrelationid; 

// Definition

WDFAPI PfnMbbrequestgetcorrelationid 
(
	PMBB_DRIVER_GLOBALS DriverGlobals
	MBBREQUEST Request
)
{...}

```

## -parameters

### -param DriverGlobals: 
### -param Request: 



## -returns

Returns WDFAPI that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also