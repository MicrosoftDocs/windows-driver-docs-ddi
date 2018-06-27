---
UID: NC:mbbcxtypes.MBBFUNC
title: MBBFUNC
author: windows-driver-content
description: 
ms.assetid: fca2edd6-c239-47f8-b0dc-5ccc625f28ad
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: mbbcxtypes.h
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
-	mbbcxtypes.h
api_name: 
-	MBBFUNC
product: Windows
targetos: Windows
---

# MBBFUNC callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

MBBFUNC Mbbfunc; 

// Definition

VOID Mbbfunc 
(
	VOID Arg1
)
{...}

```

## -parameters

### -param Arg1: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also