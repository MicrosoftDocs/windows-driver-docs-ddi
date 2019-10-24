---
UID: NS:avcstrm._AVC_STREAM_REQUEST_BLOCK
title: _AVC_STREAM_REQUEST_BLOCK (avcstrm.h)
description: The AVC_STREAM_REQUEST_BLOCK structure describes an AV/C streaming request to be processed by avcstrm.sys.
old-location: stream\avc_stream_request_block.htm
tech.root: stream
ms.assetid: 077fc4ab-94a0-42eb-a0c5-684e447cb038
ms.date: 04/23/2018
ms.keywords: "*PAVC_STREAM_REQUEST_BLOCK, AVC_STREAM_REQUEST_BLOCK, AVC_STREAM_REQUEST_BLOCK structure [Streaming Media Devices], PAVC_STREAM_REQUEST_BLOCK, PAVC_STREAM_REQUEST_BLOCK structure pointer [Streaming Media Devices], _AVC_STREAM_REQUEST_BLOCK, avcsref_1ea2a63f-ba4a-4fc3-834c-0f0a88de5023.xml, avcstrm/AVC_STREAM_REQUEST_BLOCK, avcstrm/PAVC_STREAM_REQUEST_BLOCK, stream.avc_stream_request_block"
ms.topic: struct
f1_keywords:
 - "avcstrm/AVC_STREAM_REQUEST_BLOCK"
req.header: avcstrm.h
req.include-header: Avcstrm.h
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
- avcstrm.h
api_name:
- AVC_STREAM_REQUEST_BLOCK
product:
- Windows
targetos: Windows
req.typenames: AVC_STREAM_REQUEST_BLOCK, *PAVC_STREAM_REQUEST_BLOCK
---

# _AVC_STREAM_REQUEST_BLOCK structure


## -description


The AVC_STREAM_REQUEST_BLOCK structure describes an AV/C streaming request to be processed by <i>avcstrm.sys</i>.


## -struct-fields




### -field SizeOfThisBlock

Specifies the size of the request block in bytes. Do not set this value directly. Instead, use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avcstrm/nf-avcstrm-init_avcstrm_header">INIT_AVCSTRM_HEADER</a> macro.


### -field Version

Specifies the version of <i>avcstrm.sys</i> device driver interface (DDI) to service a request. Do not set this value directly. Instead, use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avcstrm/nf-avcstrm-init_avcstrm_header">INIT_AVCSTRM_HEADER</a> macro.


### -field Function

Indicates the request (function code) <i>avcstrm.sys</i> services. This must be a value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avcstrm/ne-avcstrm-_avcstrm_function">AVCSTRM_FUNCTION</a> enumeration. Do not set this value directly. Instead, use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avcstrm/nf-avcstrm-init_avcstrm_header">INIT_AVCSTRM_HEADER</a> macro.


### -field Flags

Special flags to indicate special service or deviation from standard service. This is currently not used.


### -field Status

Final status of this request.


### -field AVCStreamContext

This is context (handle) of a stream. Set this to <b>NULL</b> for the <b>AVCSTRM_OPEN</b> function code. For other function codes, this must be set to a valid value retrieved from an earlier call to AVCSTRM_OPEN.


### -field Context1

The context pointers of the client.


### -field Context2

The context pointers of the client.


### -field Context3

The context pointers of the client.


### -field Context4

The context pointers of the client.


### -field Reserved

Reserved. Do not use.


### -field CommandData

This is a union of command data to be passed to <i>avcstrm.sys</i> for service.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
StreamState

</td>
<td>
Specifies the current state of the specified stream. This is used with the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-get-state">AVCSTRM_GET_STATE</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-set-state">AVCSTRM_SET_STATE</a> function codes.

</td>
</tr>
<tr>
<td>
OpenStruct

</td>
<td>
Specifies a description of a stream to open. This is used with the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-open">AVCSTRM_OPEN</a> function code.

</td>
</tr>
<tr>
<td>
BufferStruct

</td>
<td>
Specifies a description of a buffer used to read or write data from/to a specified stream. This is used with the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-read">AVCSTRM_READ</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-write">AVCSTRM_WRITE</a> function codes.

</td>
</tr>
</table>
 


### -field CommandData.StreamState

 


### -field CommandData.OpenStruct

 


### -field CommandData.BufferStruct

 


### -field _tagCommandData

 




## -remarks



The AVC_STREAM_REQUEST_BLOCK is the primary structure used by a subunit driver to interface with <i>avcstrm.sys</i>.

Every AV/C stream request is described by this structure. This structure is passed as part of the IRP to <i>avcstrm.sys</i> for service..

To use this structure, set the IRP's <b>Irp->Parameters->Others.Argument1</b> member to an allocated and initialized AVC_STREAM_REQUEST_BLOCK that describes the request (functionality) that the subunit driver wants <i>avcstrm.sys</i> to service.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-abort-streaming">AVCSTRM_ABORT_STREAMING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avcstrm/ns-avcstrm-_avcstrm_buffer_struct">AVCSTRM_BUFFER_STRUCT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-close">AVCSTRM_CLOSE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avcstrm/ne-avcstrm-_avcstrm_function">AVCSTRM_FUNCTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-get-property">AVCSTRM_GET_PROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-get-state">AVCSTRM_GET_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-open">AVCSTRM_OPEN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avcstrm/ns-avcstrm-_avcstrm_open_struct">AVCSTRM_OPEN_STRUCT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-read">AVCSTRM_READ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-set-property">AVCSTRM_SET_PROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-set-state">AVCSTRM_SET_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avcstrm-write">AVCSTRM_WRITE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ne-ks-ksstate">KSSTATE</a>
 

 

