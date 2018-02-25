---
UID: NE:strmini.STREAM_BUFFER_TYPE
title: STREAM_BUFFER_TYPE
author: windows-driver-content
description: This enumeration defines the buffer types for StreamClassGetPhysicalAddress.
old-location: stream\stream_buffer_type.htm
old-project: stream
ms.assetid: 7C9E1D94-BF59-4302-BEE8-24546C8AE7E6
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, A, B, DmaBuffer, E, F, M, P, PerRequestExtension, R, S, SRBDataBuffer, STREAM_BUFFER_TYPE, STREAM_BUFFER_TYPE enumeration [Streaming Media Devices], T, U, Y, _, stream.stream_buffer_type, strmini/DmaBuffer, strmini/PerRequestExtension, strmini/SRBDataBuffer, strmini/STREAM_BUFFER_TYPE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: strmini.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Strmini.h
apiname:
-	STREAM_BUFFER_TYPE
product: Windows
targetos: Windows
req.typenames: STREAM_BUFFER_TYPE
req.product: Windows 10 or later.
---

# STREAM_BUFFER_TYPE enumeration


## -description


This enumeration defines the buffer types for <a href="https://docs.microsoft.com/en-us/dotnet/core/rid-catalog">StreamClassGetPhysicalAddress</a>.


## -syntax


````
typedef enum  { 
  PerRequestExtension,
  DmaBuffer,
  SRBDataBuffer
} STREAM_BUFFER_TYPE;
````


## -enum-fields




### -field PerRequestExtension

Indicates the physical address of the SRB extension.


### -field DmaBuffer

Indicates the physical address of the DMA buffer.


### -field SRBDataBuffer

Indicates the physical address of a data buffer.

