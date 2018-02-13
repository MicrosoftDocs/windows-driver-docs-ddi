---
UID: NC:hdaudio.PALLOCATE_CAPTURE_DMA_ENGINE
title: PALLOCATE_CAPTURE_DMA_ENGINE
author: windows-driver-content
description: The AllocateCaptureDmaEngine routine allocates a DMA engine for a capture stream.The function pointer type for an AllocateCaptureDmaEngine routine is defined as follows.
old-location: audio\allocatecapturedmaengine.htm
old-project: audio
ms.assetid: 038e52be-04db-41c2-aa19-85bc4eb8bc57
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: audio.allocatecapturedmaengine, AllocateCaptureDmaEngine callback function [Audio Devices], AllocateCaptureDmaEngine, PALLOCATE_CAPTURE_DMA_ENGINE, PALLOCATE_CAPTURE_DMA_ENGINE, hdaudio/AllocateCaptureDmaEngine, aud-prop2_0eb8fa9c-157f-4979-8db1-362ec56cd3c3.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: hdaudio.h
req.include-header: Hdaudio.h
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	hdaudio.h
apiname:
-	AllocateCaptureDmaEngine
product: Windows
targetos: Windows
req.typenames: SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
---

# PALLOCATE_CAPTURE_DMA_ENGINE callback


## -description


The <code>AllocateCaptureDmaEngine</code> routine allocates a DMA engine for a capture stream.

The function pointer type for an <code>AllocateCaptureDmaEngine</code> routine is defined as follows.


## -prototype


````
PALLOCATE_CAPTURE_DMA_ENGINE AllocateCaptureDmaEngine;

NTSTATUS AllocateCaptureDmaEngine(
  _In_  PVOID                     context,
  _In_  UCHAR                     codecAddress,
  _In_  PHDAUDIO_STREAM_FORMAT    streamFormat,
  _Out_ PHANDLE                   handle,
  _Out_ PHDAUDIO_CONVERTER_FORMAT converterFormat
)
{ ... }
````


## -parameters




### -param _context [in]

Specifies the context value from the <b>Context</b> member of the <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface.md">HDAUDIO_BUS_INTERFACE</a><u>, </u><a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a> or <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a> structure.


### -param CodecAddress


### -param StreamFormat


### -param Handle


### -param ConverterFormat








#### - codecAddress [in]

Specifies a codec address. This parameter identifies the serial data in (SDI) line on which the codec supplies the capture data to the HD Audio bus controller. A bus controller with <i>n</i> SDI pins can support up to <i>n</i> codecs with addresses ranging from 0 to <i>n</i>-1.


#### - streamFormat [in]

Specifies the requested stream format. This parameter points to a caller-allocated structure of type <a href="..\hdaudio\ns-hdaudio-_hdaudio_stream_format.md">HDAUDIO_STREAM_FORMAT</a> that specifies a data format for the stream.


#### - handle [out]

Retrieves the handle to the DMA engine. This parameter points to a caller-allocated HANDLE variable into which the routine writes a handle that identifies the DMA engine.


#### - converterFormat [out]

Retrieves the converter format. This parameter points to a caller-allocated structure of type <a href="..\hdaudio\ns-hdaudio-_hdaudio_converter_format.md">HDAUDIO_CONVERTER_FORMAT</a> into which the routine writes the encoded format.


## -returns



<code>AllocateCaptureDmaEngine</code> returns STATUS_SUCCESS if the call succeeds in reserving a DMA engine. Otherwise, possible return values include the error codes in the following table.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the DMA engine is unable to allocate sufficient internal FIFO storage to support the requested stream format.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates that either no DMA engine is available or the request exceeds the available bandwidth resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Indicates that one of the parameter values is incorrect (invalid parameter value or bad pointer).

</td>
</tr>
</table>
 




## -remarks



This routine allocates a capture DMA engine and specifies the data format for the stream. If successful, the routine outputs a handle that the caller subsequently uses to identify the DMA engine.

The <code>AllocateCaptureDmaEngine</code> routine reserves hardware resources (the DMA engine) but does not configure the DMA hardware. After calling this routine to reserve a DMA engine, a function driver must assign a DMA buffer to the DMA engine and configure the engine to use the buffer:

<ul>
<li>
If using the HDAUDIO_BUS_INTERFACE version of the HD Audio DDI, the function driver calls the <a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer.md">AllocateDmaBuffer</a> routine to have the HD Audio bus driver allocate a data buffer for DMA transfers and set up the DMA engine to use the buffer.

</li>
<li>
If using the HDAUDIO_BUS_INTERFACE_BDL version of the DDI, the function driver calls <a href="..\hdaudio\nc-hdaudio-pallocate_contiguous_dma_buffer.md">AllocateContiguousDmaBuffer</a> to allocate the DMA buffer and calls the <a href="..\hdaudio\nc-hdaudio-psetup_dma_engine_with_bdl.md">SetupDmaEngineWithBdl</a> routine to set up the DMA engine to use the buffer.

</li>
</ul>
The <i>streamFormat</i> parameter specifies the data format for the capture stream. Following the call to <code>AllocateCaptureDmaEngine</code>, the stream's format can be changed by calling <a href="..\hdaudio\nc-hdaudio-pchange_bandwidth_allocation.md">ChangeBandwidthAllocation</a>.

Through the <i>handle</i> parameter, the routine outputs a handle that the caller uses to identify the allocated DMA engine in subsequent calls to <b>AllocateDmaBuffer</b>, <b>ChangeBandwidthAllocation</b>, <b>FreeDmaBuffer</b>, <b>SetupDmaEngineWithBdl</b>, and <b>SetDmaEngineState</b>. The function driver frees the handle by calling <b>FreeDmaEngine</b>.

Through the <i>converterFormat</i> parameter, the routine outputs a stream descriptor value that the caller can use to program the input converters. The routine encodes the information from the <i>streamFormat</i> parameter into a 16-bit integer. For more information, see <a href="..\hdaudio\ns-hdaudio-_hdaudio_converter_format.md">HDAUDIO_CONVERTER_FORMAT</a>.

Immediately following a successful call to <code>AllocateCaptureDmaEngine</code>, the DMA engine is in the reset stream state. Before calling <b>SetDmaEngineState</b> to change the DMA engine to the running, paused, or stopped state, the client must first allocate a DMA buffer for the engine.

A Windows Driver Model (WDM) audio driver calls <code>AllocateCaptureDmaEngine</code> at pin-creation time during execution of its <b>NewStream</b> method (for example, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536735">IMiniportWavePci::NewStream</a>).




## -see-also

<a href="..\hdaudio\ns-hdaudio-_hdaudio_converter_format.md">HDAUDIO_CONVERTER_FORMAT</a>



<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a>



<a href="..\hdaudio\nc-hdaudio-pset_dma_engine_state.md">SetDmaEngineState</a>



<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a>



<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface.md">HDAUDIO_BUS_INTERFACE</a>



<a href="..\hdaudio\nc-hdaudio-psetup_dma_engine_with_bdl.md">SetupDmaEngineWithBdl</a>



<a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer.md">AllocateDmaBuffer</a>



<a href="..\hdaudio\ns-hdaudio-_hdaudio_stream_format.md">HDAUDIO_STREAM_FORMAT</a>



<a href="..\hdaudio\nc-hdaudio-pfree_dma_engine.md">FreeDmaEngine</a>



<a href="..\hdaudio\nc-hdaudio-pallocate_contiguous_dma_buffer.md">AllocateContiguousDmaBuffer</a>



<a href="..\hdaudio\nc-hdaudio-pchange_bandwidth_allocation.md">ChangeBandwidthAllocation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PALLOCATE_CAPTURE_DMA_ENGINE callback function%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

