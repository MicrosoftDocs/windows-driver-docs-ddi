---
UID: NC:mbbcx.PFN_MBBREQUESTCOMPLETEWITHINFORMATION
title: PFN_MBBREQUESTCOMPLETEWITHINFORMATION
author: windows-driver-content
description: 
ms.assetid: b56438dd-0ec6-427f-ac0c-5ab02564d676
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
-	PFN_MBBREQUESTCOMPLETEWITHINFORMATION
product: Windows
targetos: Windows
---

# PFN_MBBREQUESTCOMPLETEWITHINFORMATION callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFN_MBBREQUESTCOMPLETEWITHINFORMATION PfnMbbrequestcompletewithinformation; 

// Definition

WDFAPI PfnMbbrequestcompletewithinformation 
(
	PMBB_DRIVER_GLOBALS DriverGlobals
	MBBREQUEST Request
	NTSTATUS NtStatus
	ULONG_PTR Information
)
{...}

```

## -parameters

### -param DriverGlobals: 
### -param Request: 
### -param NtStatus: 
### -param Information: 



## -returns

Returns WDFAPI that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also