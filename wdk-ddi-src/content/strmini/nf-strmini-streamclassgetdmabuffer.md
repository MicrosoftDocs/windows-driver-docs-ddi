---
UID: NF:strmini.StreamClassGetDmaBuffer
title: StreamClassGetDmaBuffer function (strmini.h)
description: The StreamClassGetDmaBuffer routine returns a pointer to the DMA buffer that the class driver allocates for the minidriver.
old-location: stream\streamclassgetdmabuffer.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["StreamClassGetDmaBuffer function"]
ms.keywords: StreamClassGetDmaBuffer, StreamClassGetDmaBuffer routine [Streaming Media Devices], strclass-routines_d010423c-9c48-4dee-8ca3-f4b2854d14c9.xml, stream.streamclassgetdmabuffer, strmini/StreamClassGetDmaBuffer
req.header: strmini.h
req.include-header: Strmini.h
req.target-type: Desktop
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
req.lib: Stream.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - StreamClassGetDmaBuffer
 - strmini/StreamClassGetDmaBuffer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Stream.lib
 - Stream.dll
api_name:
 - StreamClassGetDmaBuffer
---

# StreamClassGetDmaBuffer function


## -description

The <b>StreamClassGetDmaBuffer</b> routine returns a pointer to the DMA buffer that the class driver allocates for the minidriver.

## -parameters

### -param HwDeviceExtension 

[in]
Pointer to the minidriver's device extension. The minidriver specifies the size of this buffer in the <a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself via <a href="/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassregisteradapter">StreamClassRegisterMinidriver</a>. The class driver then passes pointers to the buffer in the <b>HwDeviceExtension</b> member of the <a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_request_block">HW_STREAM_REQUEST_BLOCK</a>, <a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_object">HW_STREAM_OBJECT</a>, <a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_time_context">HW_TIME_CONTEXT</a>, and <a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_port_configuration_information">PORT_CONFIGURATION_INFORMATION</a> structures it passes to the minidriver.

## -returns

<b>StreamClassGetDmaBuffer</b> returns a pointer to the DMA buffer.

## -remarks

The minidriver specifies the size of the DMA buffer in the <b>DmaBufferSize</b> member of its <a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a>
