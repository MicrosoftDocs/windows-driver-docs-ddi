---
UID: NC:iddcx.PFN_IDDCXADAPTERSETRENDERADAPTER
title: *PFN_IDDCXADAPTERSETRENDERADAPTER
author: windows-driver-content
description: 
tech.root: display
ms.assetid: 0a4cd4b6-a6a2-4f23-9775-bddab232fded
ms.author: windowsdriverdev
ms.date: 08/19/2019
ms.topic: callback
f1_keywords:
 - "iddcx/*PFN_IDDCXADAPTERSETRENDERADAPTER"
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: iddcx.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
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
 - apiref
api_type: 
 - UserDefined
api_location: 
 - iddcx.h
api_name: 
 - *PFN_IDDCXADAPTERSETRENDERADAPTER
product: 
 - Windows
targetos: Windows
ms.custom: 19H1
---

# *PFN_IDDCXADAPTERSETRENDERADAPTER callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

*PFN_IDDCXADAPTERSETRENDERADAPTER *PfnIddcxadaptersetrenderadapter; 

// Definition

VOID *PfnIddcxadaptersetrenderadapter 
(
	PIDD_DRIVER_GLOBALS DriverGlobals
	IDDCX_ADAPTER AdapterObject
	 const IDARG_IN_ADAPTERSETRENDERADAPTER *pInArgs
)
{...}

```

## -parameters

### -param DriverGlobals

### -param AdapterObject

### -param *pInArgs



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also
