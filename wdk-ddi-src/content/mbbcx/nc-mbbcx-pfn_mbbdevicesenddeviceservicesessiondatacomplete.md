---
UID: NC:mbbcx.PFN_MBBDEVICESENDDEVICESERVICESESSIONDATACOMPLETE
title: PFN_MBBDEVICESENDDEVICESERVICESESSIONDATACOMPLETE
author: windows-driver-content
description: 
ms.assetid: 9e57f8b6-07a0-44b1-970c-9ff1a8be7511
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
-	PFN_MBBDEVICESENDDEVICESERVICESESSIONDATACOMPLETE
product: Windows
targetos: Windows
---

# PFN_MBBDEVICESENDDEVICESERVICESESSIONDATACOMPLETE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFN_MBBDEVICESENDDEVICESERVICESESSIONDATACOMPLETE PfnMbbdevicesenddeviceservicesessiondatacomplete; 

// Definition

WDFAPI PfnMbbdevicesenddeviceservicesessiondatacomplete 
(
	PMBB_DRIVER_GLOBALS DriverGlobals
	WDFMEMORY Data
	NTSTATUS NtStatus
)
{...}

```

## -parameters

### -param DriverGlobals: 
### -param Data: 
### -param NtStatus: 



## -returns

Returns WDFAPI that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also