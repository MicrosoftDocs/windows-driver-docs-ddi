---
UID: NS:avcstrm._AVC_STREAM_REQUEST_BLOCK
title: AVC_STREAM_REQUEST_BLOCK (avcstrm.h)
description: The AVC_STREAM_REQUEST_BLOCK structure describes an AV/C streaming request to be processed by avcstrm.sys.
tech.root: stream
ms.date: 03/03/2023
keywords: ["AVC_STREAM_REQUEST_BLOCK structure"]
ms.keywords: "*PAVC_STREAM_REQUEST_BLOCK, AVC_STREAM_REQUEST_BLOCK, AVC_STREAM_REQUEST_BLOCK structure [Streaming Media Devices], PAVC_STREAM_REQUEST_BLOCK, PAVC_STREAM_REQUEST_BLOCK structure pointer [Streaming Media Devices], _AVC_STREAM_REQUEST_BLOCK, avcsref_1ea2a63f-ba4a-4fc3-834c-0f0a88de5023.xml, avcstrm/AVC_STREAM_REQUEST_BLOCK, avcstrm/PAVC_STREAM_REQUEST_BLOCK, stream.avc_stream_request_block"
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
targetos: Windows
req.typenames: AVC_STREAM_REQUEST_BLOCK, *PAVC_STREAM_REQUEST_BLOCK
f1_keywords:
 - _AVC_STREAM_REQUEST_BLOCK
 - avcstrm/_AVC_STREAM_REQUEST_BLOCK
 - PAVC_STREAM_REQUEST_BLOCK
 - avcstrm/PAVC_STREAM_REQUEST_BLOCK
 - AVC_STREAM_REQUEST_BLOCK
 - avcstrm/AVC_STREAM_REQUEST_BLOCK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - avcstrm.h
api_name:
 - _AVC_STREAM_REQUEST_BLOCK
 - PAVC_STREAM_REQUEST_BLOCK
 - AVC_STREAM_REQUEST_BLOCK
---

## -description

The AVC_STREAM_REQUEST_BLOCK structure describes an AV/C streaming request to be processed by *avcstrm.sys*.

## -struct-fields

### -field SizeOfThisBlock

Specifies the size of the request block in bytes. Do not set this value directly. Instead, use the [INIT_AVCSTRM_HEADER](/windows-hardware/drivers/ddi/avcstrm/nf-avcstrm-init_avcstrm_header) macro.

### -field Version

Specifies the version of *avcstrm.sys* device driver interface (DDI) to service a request. Do not set this value directly. Instead, use the [INIT_AVCSTRM_HEADER](/windows-hardware/drivers/ddi/avcstrm/nf-avcstrm-init_avcstrm_header) macro.

### -field Function

Indicates the request (function code) *avcstrm.sys* services. This must be a value from the [AVCSTRM_FUNCTION](/windows-hardware/drivers/ddi/avcstrm/ne-avcstrm-_avcstrm_function) enumeration. Do not set this value directly. Instead, use the [INIT_AVCSTRM_HEADER](/windows-hardware/drivers/ddi/avcstrm/nf-avcstrm-init_avcstrm_header) macro.

### -field Flags

Special flags to indicate special service or deviation from standard service. This is currently not used.

### -field Status

Final status of this request.

### -field AVCStreamContext

This is context (handle) of a stream. Set this to **NULL** for the **AVCSTRM_OPEN** function code. For other function codes, this must be set to a valid value retrieved from an earlier call to AVCSTRM_OPEN.

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

This is a union of command data to be passed to *avcstrm.sys* for service.

| Flag | Description |
|---|---|
| StreamState | Specifies the current state of the specified stream. This is used with the [AVCSTRM_GET_STATE](/windows-hardware/drivers/stream/avcstrm-get-state) and [AVCSTRM_SET_STATE](/windows-hardware/drivers/stream/avcstrm-set-state) function codes. |
| OpenStruct | Specifies a description of a stream to open. This is used with the [AVCSTRM_OPEN](/windows-hardware/drivers/stream/avcstrm-open) function code. |
| BufferStruct | Specifies a description of a buffer used to read or write data from/to a specified stream. This is used with the [AVCSTRM_READ](/windows-hardware/drivers/stream/avcstrm-read) and [AVCSTRM_WRITE](/windows-hardware/drivers/stream/avcstrm-write) function codes. |

### -field CommandData.StreamState

Defines the **KSSTATE** member **StreamState**.

### -field CommandData.OpenStruct

Defines the **AVCSTRM_OPEN_STRUCT** member **OpenStruct**.

### -field CommandData.BufferStruct

Defines the **AVCSTRM_BUFFER_STRUCT** member **BufferStruct**.

### -field _tagCommandData

Defines the **_tagCommandData** member **_tagCommandData**.

## -remarks

The AVC_STREAM_REQUEST_BLOCK is the primary structure used by a subunit driver to interface with *avcstrm.sys*.

Every AV/C stream request is described by this structure. This structure is passed as part of the IRP to *avcstrm.sys* for service..

To use this structure, set the IRP's **Irp->Parameters->Others.Argument1** member to an allocated and initialized AVC_STREAM_REQUEST_BLOCK that describes the request (functionality) that the subunit driver wants *avcstrm.sys* to service.

## -see-also

[AVCSTRM_ABORT_STREAMING](/windows-hardware/drivers/stream/avcstrm-abort-streaming)

[AVCSTRM_BUFFER_STRUCT](/windows-hardware/drivers/ddi/avcstrm/ns-avcstrm-_avcstrm_buffer_struct)

[AVCSTRM_CLOSE](/windows-hardware/drivers/stream/avcstrm-close)

[AVCSTRM_FUNCTION](/windows-hardware/drivers/ddi/avcstrm/ne-avcstrm-_avcstrm_function)

[AVCSTRM_GET_PROPERTY](/windows-hardware/drivers/stream/avcstrm-get-property)

[AVCSTRM_GET_STATE](/windows-hardware/drivers/stream/avcstrm-get-state)

[AVCSTRM_OPEN](/windows-hardware/drivers/stream/avcstrm-open)

[AVCSTRM_OPEN_STRUCT](/windows-hardware/drivers/ddi/avcstrm/ns-avcstrm-_avcstrm_open_struct)

[AVCSTRM_READ](/windows-hardware/drivers/stream/avcstrm-read)

[AVCSTRM_SET_PROPERTY](/windows-hardware/drivers/stream/avcstrm-set-property)

[AVCSTRM_SET_STATE](/windows-hardware/drivers/stream/avcstrm-set-state)

[AVCSTRM_WRITE](/windows-hardware/drivers/stream/avcstrm-write)

[KSSTATE](/windows-hardware/drivers/ddi/ks/ne-ks-ksstate)
