---
UID: NE:strmini.STREAM_BUFFER_TYPE
title: STREAM_BUFFER_TYPE (strmini.h)
description: This enumeration defines the buffer types for StreamClassGetPhysicalAddress.
old-location: stream\stream_buffer_type.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["STREAM_BUFFER_TYPE enumeration"]
ms.keywords: DmaBuffer, PerRequestExtension, SRBDataBuffer, STREAM_BUFFER_TYPE, STREAM_BUFFER_TYPE enumeration [Streaming Media Devices], stream.stream_buffer_type, strmini/DmaBuffer, strmini/PerRequestExtension, strmini/SRBDataBuffer, strmini/STREAM_BUFFER_TYPE
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
targetos: Windows
req.typenames: STREAM_BUFFER_TYPE
f1_keywords:
 - STREAM_BUFFER_TYPE
 - strmini/STREAM_BUFFER_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Strmini.h
api_name:
 - STREAM_BUFFER_TYPE
---

# STREAM_BUFFER_TYPE enumeration


## -description

This enumeration defines the buffer types for <a href="/dotnet/core/rid-catalog">StreamClassGetPhysicalAddress</a>.

## -enum-fields

### -field PerRequestExtension

Indicates the physical address of the SRB extension.

### -field DmaBuffer

Indicates the physical address of the DMA buffer.

### -field SRBDataBuffer

Indicates the physical address of a data buffer.

