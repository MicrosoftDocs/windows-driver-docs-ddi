---
UID: NF:ksproxy.IKsInterfaceHandler.KsProcessMediaSamples
title: IKsInterfaceHandler::KsProcessMediaSamples (ksproxy.h)
description: The KsProcessMediaSamples method processes media samples.
old-location: stream\iksinterfacehandler_ksprocessmediasamples.htm
tech.root: stream
ms.assetid: 3f0982d8-4ac3-40f6-8587-624c26d25510
ms.date: 04/23/2018
ms.keywords: IKsInterfaceHandler interface [Streaming Media Devices],KsProcessMediaSamples method, IKsInterfaceHandler.KsProcessMediaSamples, IKsInterfaceHandler::KsProcessMediaSamples, KsProcessMediaSamples, KsProcessMediaSamples method [Streaming Media Devices], KsProcessMediaSamples method [Streaming Media Devices],IKsInterfaceHandler interface, ksproxy/IKsInterfaceHandler::KsProcessMediaSamples, ksproxy_929792a7-d5c4-4568-9178-866b9738079b.xml, stream.iksinterfacehandler_ksprocessmediasamples
ms.topic: method
req.header: ksproxy.h
req.include-header: Ksproxy.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- ksproxy.h
api_name:
- IKsInterfaceHandler.KsProcessMediaSamples
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsInterfaceHandler::KsProcessMediaSamples


## -description


The <b>KsProcessMediaSamples</b> method processes media samples.


## -parameters




### -param KsDataTypeHandler [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nn-ksproxy-iksdatatypehandler">IKsDataTypeHandler</a> interface for the data type handler that handles the type of media listed at <i>SampleList</i>. This data type handler has specific information about the media type being streamed.


### -param SampleList [in]

Pointer to a buffer that contains an array of pointers to the <b>IMediaSample</b> interfaces for the list of media samples to process. 


### -param SampleCount [in, out]

Pointer to a variable that initially contains the number of samples in the list at <i>SampleList</i> and, on return, receives the actual number of samples processed.


### -param IoOperation [in]

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
 


### -param StreamSegment [out]

Pointer to a buffer that receives a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/ns-ksproxy-_ksstream_segment">KSSTREAM_SEGMENT</a> structure that contains header information for a stream segment that is sent to the kernel-mode pin. 


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -remarks



The <b>KsProcessMediaSamples</b> method moves samples from or to a previously assigned filter pin. A stream header is initialized to represent each media sample in the stream segment. The input and output (I/O) are then performed, the count of wait items is incremented, and the proxy I/O thread waits for completion.

The <b>KsProcessMediaSamples</b> method calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nf-ksproxy-iksdatatypehandler-ksqueryextendedsize">KsQueryExtendedSize</a> method of the received <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nn-ksproxy-iksdatatypehandler">IKsDataTypeHandler</a> interface to retrieve the size of the extended header. If an extended header size is not specified, <b>KsProcessMediaSamples</b> discards the pointer to the <b>IKsDataTypeHandler</b> interface. If an extended header size is specified, <b>KsProcessMediaSamples</b> holds the pointer to the <b>IKsDataTypeHandler</b> interface until processing of the media samples is complete. The <b>KsProcessMediaSamples</b> method then allocates the stream headers with the appropriate header sizes. For each media sample, <b>KsProcessMediaSamples</b> initializes the header, copies data pointers, sets time stamps, and so on. Each sample is then added to the sample list. If it is a write operation, the sample is held by incrementing the reference count. 

For more information about <b>IMediaSample</b>, see the Microsoft Windows SDK documentation.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nn-ksproxy-iksdatatypehandler">IKsDataTypeHandler</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nf-ksproxy-iksdatatypehandler-ksqueryextendedsize">IKsDataTypeHandler::KsQueryExtendedSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/ns-ksproxy-_ksstream_segment">KSSTREAM_SEGMENT</a>
 

 

