---
UID: NC:usbcamdi.PSTREAM_RECEIVE_PACKET
title: PSTREAM_RECEIVE_PACKET (usbcamdi.h)
description: 
ms.assetid: 2ae5c8c4-9951-4424-90e8-25fd25a48bb2
ms.date: 10/19/2018
keywords: ["PSTREAM_RECEIVE_PACKET callback function"]
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
targetos: Windows
ms.custom: RS5
f1_keywords:
 - PSTREAM_RECEIVE_PACKET
 - usbcamdi/PSTREAM_RECEIVE_PACKET
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - usbcamdi.h
api_name:
 - PSTREAM_RECEIVE_PACKET
---

# PSTREAM_RECEIVE_PACKET callback function


## -description

## -parameters

### -param Srb

### -param DeviceContext

### -param Completed

## -syntax

```cpp
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

## -remarks

## -see-also

