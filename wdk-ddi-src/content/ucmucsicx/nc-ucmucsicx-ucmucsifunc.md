---
UID: NC:ucmucsicx.UCMUCSIFUNC
title: UCMUCSIFUNC
author: windows-driver-content
description: 
ms.assetid: 8d351748-2e44-4c4b-a22c-1811fe197388
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: ucmucsicx.h
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
-	ucmucsicx.h
api_name: 
-	UCMUCSIFUNC
product: Windows
targetos: Windows
---

# UCMUCSIFUNC callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

UCMUCSIFUNC Ucmucsifunc; 

// Definition

VOID Ucmucsifunc 
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