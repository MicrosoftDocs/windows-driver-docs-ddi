---
UID: NC:usbcamdi.PSTREAM_RECEIVE_PACKET
title: PSTREAM_RECEIVE_PACKET
author: windows-driver-content
description: 
ms.assetid: 2ae5c8c4-9951-4424-90e8-25fd25a48bb2
ms.date: 
ms.topic: callback
req.header: usbcamdi.h
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
-	usbcamdi.h
api_name: 
-	PSTREAM_RECEIVE_PACKET
product:
-	Windows
targetos: Windows
---

# PSTREAM_RECEIVE_PACKET callback function

## -description

## -prototype

```
//Declaration

PSTREAM_RECEIVE_PACKET PstreamReceivePacket; 

// Definition

VOID PstreamReceivePacket 
(
	PVOID Srb
	PVOID DeviceContext
	PBOOLEAN Completed
)
{...}

```

## -parameters

### -param Srb: 
### -param DeviceContext: 
### -param Completed: 


## -returns

## -remarks

## -see-also
