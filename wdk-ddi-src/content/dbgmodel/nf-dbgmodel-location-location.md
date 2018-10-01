---
UID: NF:dbgmodel.Location.Location
title: Location function
author: windows-driver-content
description: TBD
ms.assetid: e50b6f55-a47e-4fbc-b7f1-041cbccf9ea5
ms.author: windowsdriverdev
ms.date: 09/28/2018
ms.topic: function
ms.keywords: Location
req.header: dbgmodel.h
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
-	
api_location: 
-	
api_name: 
-	Location
product: Windows
targetos: Windows


tech.root: debugger
---

# Location function


## -description

Constructs a location from an offset into the virtual address space of the target.

Default constructs an equivalent nullptr.

## -parameters
 None


## -returns
This function does not return value.

## -remarks
Defines the location for an object.  This particular variant of Location is the C-COM access struct.
Note that a location only has meaning in conjunction with a host context.  It is a location within
a context.  When performing an operation on the location (reading bytes, writing bytes, etc...), 
a valid host context must be supplied.

## -see-also
[dbgmodel.h header](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgmodel/)

