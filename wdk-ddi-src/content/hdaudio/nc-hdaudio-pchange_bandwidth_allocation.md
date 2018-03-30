---
UID: NC:hdaudio.PCHANGE_BANDWIDTH_ALLOCATION
title: PCHANGE_BANDWIDTH_ALLOCATION
author: windows-driver-content
description: The ChangeBandwidthAllocation routine changes a DMA engine's bandwidth allocation on the HD Audio Link.The function pointer type for a ChangeBandwidthAllocation routine is defined as follows.
old-location: audio\changebandwidthallocation.htm
old-project: audio
ms.assetid: 4dcf8fb6-71f5-4e11-a92a-0292c2a1515c
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: ChangeBandwidthAllocation, ChangeBandwidthAllocation callback function [Audio Devices], PCHANGE_BANDWIDTH_ALLOCATION, aud-prop2_3d85fecb-4617-404b-951b-7457f9e650cc.xml, audio.changebandwidthallocation, hdaudio/ChangeBandwidthAllocation
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	hdaudio.h
api_name:
-	ChangeBandwidthAllocation
product: Windows
targetos: Windows
req.typenames: SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
---

# PCHANGE_BANDWIDTH_ALLOCATION callback


## -description


The <code>ChangeBandwidthAllocation</code> routine changes a DMA engine's bandwidth allocation on the HD Audio Link.

The function pointer type for a <code>ChangeBandwidthAllocation</code> routine is defined as follows.


## -parameters




### -param _context [in]

Specifies the context value from the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536413">HDAUDIO_BUS_INTERFACE</a><u>, </u><a href="https://msdn.microsoft.com/library/windows/hardware/ff536418">HDAUDIO_BUS_INTERFACE_V2</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff536416">HDAUDIO_BUS_INTERFACE_BDL</a> structure.


### -param Handle [in]

Handle identifying the DMA engine. This handle value was obtained from a previous call to <a href="https://msdn.microsoft.com/038e52be-04db-41c2-aa19-85bc4eb8bc57">AllocateCaptureDmaEngine</a> or <a href="https://msdn.microsoft.com/fb2a64ca-7e8e-4352-86c6-b9500e535c75">AllocateRenderDmaEngine</a>.


### -param StreamFormat [in]

Specifies the requested stream format. This parameter points to a caller-allocated structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff536430">HDAUDIO_STREAM_FORMAT</a> that specifies a data format for the stream.


### -param ConverterFormat [out]

Retrieves the converter format. This parameter points to a caller-allocated structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff536426">HDAUDIO_CONVERTER_FORMAT</a> into which the routine writes the encoded format. For more information, see the following Remarks section.


## -returns



<code>ChangeBandwidthAllocation</code> returns STATUS_SUCCESS if the call succeeds. Otherwise, the routine returns an appropriate error code. The following table shows some of the possible return error codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the caller is running at an IRQL that is too high.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the <i>handle</i> parameter value is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Indicates that one of the parameter values is not correct (bad pointer or invalid stream format).

</td>
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
Indicates that insufficient bandwidth is available to satisfy the request.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the stream is not in the reset state or that a buffer is still allocated for the DMA engine.

</td>
</tr>
</table>
 




## -remarks



The caller obtains an initial bandwidth allocation for a DMA engine by calling <a href="https://msdn.microsoft.com/038e52be-04db-41c2-aa19-85bc4eb8bc57">AllocateCaptureDmaEngine</a> or <a href="https://msdn.microsoft.com/fb2a64ca-7e8e-4352-86c6-b9500e535c75">AllocateRenderDmaEngine</a>. Thereafter, the caller can change the bandwidth allocation by calling <code>ChangeBandwidthAllocation</code>.

Through the <i>converterFormat</i> parameter, the routine outputs a stream descriptor value that the caller can use to program the input or output converters. The routine encodes the information from the <i>streamFormat</i> parameter into a 16-bit integer. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536426">HDAUDIO_CONVERTER_FORMAT</a>.

This routine fails and returns error code STATUS_INVALID_DEVICE_REQUEST in either of the following circumstances:

<ul>
<li>
Any previously allocated DMA buffer has not been freed (by calling <a href="https://msdn.microsoft.com/658e32d2-40e2-4479-8212-df7140fe6b74">FreeDmaBuffer</a> or <a href="https://msdn.microsoft.com/7aaf98cc-8a94-44e6-9fef-76e00db17405">FreeContiguousDmaBuffer</a>).

</li>
<li>
The stream is in a state other than reset.

</li>
</ul>
If the <code>ChangeBandwidthAllocation</code> call fails, the existing bandwidth reservation remains in effect. The bandwidth allocation changes only if the call succeeds.

In Windows Vista and later, a wave miniport driver calls this routine during execution of its <b>SetFormat</b> method (after calling one of the Allocate<i>Xxx</i>DmaEngine routines in the HD Audio DDI). For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536732">IMiniportWavePciStream::SetFormat</a>.




## -see-also




<a href="https://msdn.microsoft.com/038e52be-04db-41c2-aa19-85bc4eb8bc57">AllocateCaptureDmaEngine</a>



<a href="https://msdn.microsoft.com/fb2a64ca-7e8e-4352-86c6-b9500e535c75">AllocateRenderDmaEngine</a>



<a href="https://msdn.microsoft.com/7aaf98cc-8a94-44e6-9fef-76e00db17405">FreeContiguousDmaBuffer</a>



<a href="https://msdn.microsoft.com/658e32d2-40e2-4479-8212-df7140fe6b74">FreeDmaBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536413">HDAUDIO_BUS_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536416">HDAUDIO_BUS_INTERFACE_BDL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536418">HDAUDIO_BUS_INTERFACE_V2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536426">HDAUDIO_CONVERTER_FORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536430">HDAUDIO_STREAM_FORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536732">IMiniportWavePciStream::SetFormat</a>
 

 

