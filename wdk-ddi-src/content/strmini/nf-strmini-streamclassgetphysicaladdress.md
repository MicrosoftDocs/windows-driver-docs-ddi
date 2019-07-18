---
UID: NF:strmini.StreamClassGetPhysicalAddress
title: StreamClassGetPhysicalAddress function (strmini.h)
description: The StreamClassGetPhysicalAddress routine translates a virtual memory address to a physical memory address and locks the corresponding physical memory for a DMA operation.
old-location: stream\streamclassgetphysicaladdress.htm
tech.root: stream
ms.assetid: 5a8e7130-00e7-4bff-8939-7cfcc1a2b9aa
ms.date: 04/23/2018
ms.keywords: StreamClassGetPhysicalAddress, StreamClassGetPhysicalAddress routine [Streaming Media Devices], strclass-routines_e8d5c2ab-3cfa-4bb7-b4f7-e57908c2c6f8.xml, stream.streamclassgetphysicaladdress, strmini/StreamClassGetPhysicalAddress
ms.topic: function
f1_keywords:
 - "strmini/StreamClassGetPhysicalAddress"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Stream.lib
- Stream.dll
api_name:
- StreamClassGetPhysicalAddress
product:
- Windows
targetos: Windows
req.typenames: 
---

# StreamClassGetPhysicalAddress function


## -description


The <b>StreamClassGetPhysicalAddress</b> routine translates a virtual memory address to a physical memory address and locks the corresponding physical memory for a DMA operation.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the minidriver's device extension. The minidriver specifies the size of this buffer in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself via <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/nf-strmini-streamclassregisteradapter">StreamClassRegisterMinidriver</a>. The class driver then passes pointers to the buffer in the <b>HwDeviceExtension</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_hw_stream_request_block">HW_STREAM_REQUEST_BLOCK</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_hw_stream_object">HW_STREAM_OBJECT</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_hw_time_context">HW_TIME_CONTEXT</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_port_configuration_information">PORT_CONFIGURATION_INFORMATION</a> structures it passes to the minidriver.


### -param HwSRB [in, optional]

Specifies a stream request block. This parameter is used only if the <i>Type</i> parameter has the value SRBDataBuffer, otherwise <i>HwSRB</i> should be <b>NULL</b>. This parameter is optional.  


### -param VirtualAddress [in]

Specifies the virtual address to be translated.


### -param Type [in]

Specifies the type of buffer pointed to by <i>VirtualAddress</i>. This value may be PerRequestExtension, DmaBuffer, or SRBDataBuffer.


### -param Length [out]

Specifies the length, in bytes, of the buffer.


## -returns



<b>StreamClassGetPhysicalAddress</b> returns the translated virtual address as a physical memory address.




## -remarks



The type of buffer to be used is specified in the <i>Type</i> parameter. The meanings of these values are shown in the following table.

<table>
<tr>
<th>Buffer Type</th>
<th>Description</th>
</tr>
<tr>
<td>
PerRequestExtension

</td>
<td>
Indicates the physical address of the SRB extension.

</td>
</tr>
<tr>
<td>
DmaBuffer

</td>
<td>
Indicates the physical address of the DMA buffer.

</td>
</tr>
<tr>
<td>
SRBDataBuffer

</td>
<td>
Indicates the physical address of the data buffer.

</td>
</tr>
</table>
 



