---
UID: NS:bdatypes._MPEG2_TRANSPORT_STRIDE
title: _MPEG2_TRANSPORT_STRIDE
author: windows-driver-content
description: The MPEG2_TRANSPORT_STRIDE structure describes the format block of the MPEG2 transport stride.
old-location: stream\mpeg2_transport_stride.htm
old-project: stream
ms.assetid: 5756bb06-8fd3-4124-b3c8-35d5ed0bd57b
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _MPEG2_TRANSPORT_STRIDE, MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdatypes.h
req.include-header: Bdatypes.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MPEG2_TRANSPORT_STRIDE
req.alt-loc: bdatypes.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
---

# _MPEG2_TRANSPORT_STRIDE structure



## -description
The MPEG2_TRANSPORT_STRIDE structure describes the format block of the MPEG2 transport stride. 



## -syntax

````
typedef struct _MPEG2_TRANSPORT_STRIDE {
  DWORD dwOffset;
  DWORD dwPacketLength;
  DWORD dwStride;
} MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE;
````


## -struct-fields

### -field dwOffset

Offset in bytes into a packet.


### -field dwPacketLength

Size in bytes of a packet.


### -field dwStride

Stride of data in a packet. 


## -remarks
The MPEG2 transport stride format block is associated with the MEDIATYPE_Stream/MEDIASUBTYPE_MPEG2_TRANSPORT_STRIDE media type. Format blocks that are associated with this media type must start with the MPEG2_TRANSPORT_STRIDE structure.</p>