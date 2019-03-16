---
UID: NS:ksproxy._KSSTREAM_SEGMENT
title: _KSSTREAM_SEGMENT (ksproxy.h)
description: The KSSTREAM_SEGMENT structure contains information that describes an I/O operation occurring on a stream.
old-location: stream\ksstream_segment.htm
tech.root: stream
ms.assetid: 433b1346-f0f1-46f7-a1d8-e6397b2f7f05
ms.date: 04/23/2018
ms.keywords: "*PKSSTREAM_SEGMENT, KSSTREAM_SEGMENT, KSSTREAM_SEGMENT structure [Streaming Media Devices], PKSSTREAM_SEGMENT, PKSSTREAM_SEGMENT structure pointer [Streaming Media Devices], _KSSTREAM_SEGMENT, ksproxy/KSSTREAM_SEGMENT, ksproxy/PKSSTREAM_SEGMENT, ksproxy_ce88ef52-d88e-4dc8-952d-53dce519518f.xml, stream.ksstream_segment"
ms.topic: struct
req.header: ksproxy.h
req.include-header: Ksproxy.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksproxy.h
api_name:
- KSSTREAM_SEGMENT
product:
- Windows
targetos: Windows
req.typenames: "*PKSSTREAM_SEGMENT, KSSTREAM_SEGMENT"
---

# _KSSTREAM_SEGMENT structure


## -description


The KSSTREAM_SEGMENT structure contains information that describes an I/O operation occurring on a stream.


## -struct-fields




### -field KsInterfaceHandler

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff559855">IKsInterfaceHandler</a> interface for the I/O operation.


### -field KsDataTypeHandler

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff559807">IKsDataTypeHandler</a> interface for the I/O operation.


### -field IoOperation

Value that specifies the type of I/O operation. This value can be one of the following values from the KSIOOPERATION enumerated type:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
<b>KsIoOperation_Write</b>

</td>
<td>
Write data to stream.

</td>
</tr>
<tr>
<td>
<b>KsIoOperation_Read</b>

</td>
<td>
Read data from stream.

</td>
</tr>
</table>
 


### -field CompletionEvent

Handle to an event that is used to signal that the I/O operation completed.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559807">IKsDataTypeHandler</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559855">IKsInterfaceHandler</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559862">IKsInterfaceHandler::KsCompleteIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559869">IKsInterfaceHandler::KsProcessMediaSamples</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560713">IKsPin::KsMediaSamplesCompleted</a>
 

 

