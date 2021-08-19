---
UID: NC:acxstreams.EVT_ACX_STREAM_ASSIGN_DRM_CONTENT_ID
tech.root: audio
title: EVT_ACX_STREAM_ASSIGN_DRM_CONTENT_ID
ms.date: 07/07/2021
targetos: Windows
description: The EVT_ACX_STREAM_ASSIGN_DRM_CONTENT_ID event tells the driver to assign a content ID for the purposes of DRM streaming.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxstreams.h
api_name:
 - EVT_ACX_STREAM_ASSIGN_DRM_CONTENT_ID
f1_keywords:
 - EVT_ACX_STREAM_ASSIGN_DRM_CONTENT_ID
 - acxstreams/EVT_ACX_STREAM_ASSIGN_DRM_CONTENT_ID
dev_langs:
 - c++
---

## -description

The EVT_ACX_STREAM_ASSIGN_DRM_CONTENT_ID event tells the driver to assign a content ID for the purposes of DRM streaming.

## -parameters

### -param Stream

A pointer to a location that receives a handle to the new ACXSTREAM Object.

An [ACXSTREAM Object]() (DocsTeam - need link to ACX Object Summary topic) that represents an audio stream created by a circuit. ACX objects are WDF object-like, i.e., the ACX driver interacts with them in the same way as WDF when creating, deleting, and interacting with them. For more information, see [WDF Architecture](/windows-hardware/drivers/wdf/kernel-mode-driver-framework-architecture) and [Framework Object Life Cycle](/windows-hardware/drivers/wdf/framework-object-life-cycle).

The ACXSTREAM Object is the driver component that’s created to represent an audio stream, created by a circuit. The Stream is composed of a list of Elements created based on the parent Circuit’s Elements.   An AcxStream aggregates zero or n AcxElements-like objects. By default, AcxElements are connected in the same order of assembly. An AcxStream is associated with only one ACX circuit. ACX supports two types of streams: basic ACX stream objects used by non-streaming circuits, and ACX RT stream objects used by streaming circuits.

### -param ContentId

Specifies a nonzero DRM content ID assigned to a KS  (TBD ACX?) audio stream by [AcxDrmCreateContentMixed](nf-acxstreams-acxdrmcreatecontentmixed.md). Note that a content ID of zero represents an audio stream with default DRM content rights, and cannot be used with this function.


### -param DrmRights

Specifies the DRM content rights that are assigned to the stream that is identified by ContentId. This parameter is a pointer to a [ACXDRMRIGHTS structure](ns-acxstreams-acxdrmrights.md).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

TBD - should we show more code here?

Example usage is shown below.

```cpp
    //
    // Init streaming callbacks.
    //
    ACX_STREAM_CALLBACKS_INIT(&streamCallbacks);
    ...
    streamCallbacks.EvtAcxStreamAssignDrmContentId = EvtStreamAssignDrmContentId;

    status = AcxStreamInitAssignAcxStreamCallbacks(StreamInit, &streamCallbacks);

...

_Use_decl_annotations_
PAGED_CODE_SEG
NTSTATUS
EvtStreamAssignDrmContentId(
    _In_ ACXSTREAM      Stream,
    _In_ ULONG          DrmContentId,
    _In_ PACXDRMRIGHTS  DrmRights
    )
{
    PSTREAM_CONTEXT ctx;

    PAGED_CODE();

    ctx = GetStreamContext(Stream);
    ASSERT(ctx);
    ASSERT(ctx->StreamEngine);

    return ctx->StreamEngine->AssignDrmContentId(DrmContentId, DrmRights);
}

```

## -see-also

[acxstreams.h header](index.md)

