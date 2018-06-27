---
UID: NC:mbbcx.PFN_MBBREQUESTCOMPLETE
title: PFN_MBBREQUESTCOMPLETE
author: windows-driver-content
description: 
ms.assetid: 284fc9ae-b70f-4f06-ae7f-0fbedd1d4d1f
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
-	PFN_MBBREQUESTCOMPLETE
product: Windows
targetos: Windows
---

# PFN_MBBREQUESTCOMPLETE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFN_MBBREQUESTCOMPLETE PfnMbbrequestcomplete; 

// Definition

WDFAPI PfnMbbrequestcomplete 
(
	PMBB_DRIVER_GLOBALS DriverGlobals
	MBBREQUEST Request
	NTSTATUS NtStatus
)
{...}

```

## -parameters

### -param DriverGlobals: 
### -param Request: 
### -param NtStatus: 



## -returns

Returns WDFAPI that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also