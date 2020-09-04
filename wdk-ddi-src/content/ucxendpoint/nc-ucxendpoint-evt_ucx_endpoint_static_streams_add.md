---
UID: NC:ucxendpoint.EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD
title: EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD (ucxendpoint.h)
description: The client driver's implementation that UCX calls to create static streams.
old-location: buses\evt_ucx_endpoint_static_streams_add.htm
tech.root: usbref
ms.assetid: 76f94f19-894a-47af-a407-8e14263f1143
ms.date: 05/07/2018
keywords: ["EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD callback function"]
ms.keywords: EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD, EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD callback, EvtUcxEndpointStaticStreamsAdd, EvtUcxEndpointStaticStreamsAdd callback function [Buses], PEVT_UCX_ENDPOINT_STATIC_STREAMS_ADD, PEVT_UCX_ENDPOINT_STATIC_STREAMS_ADD callback function pointer [Buses], buses.evt_ucx_endpoint_static_streams_add, ucxendpoint/EvtUcxEndpointStaticStreamsAdd
req.header: ucxendpoint.h
req.include-header: Ucxclass.h, Ucxendpoint.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD
 - ucxendpoint/EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ucxendpoint.h
api_name:
 - PEVT_UCX_ENDPOINT_STATIC_STREAMS_ADD
---

# EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD callback function


## -description

The client driver's implementation that UCX calls to create static streams.

## -parameters

### -param UcxEndpoint

### -param NumberOfStreams 

[in]
The number of non-default streams to create.

### -param UcxStaticStreamsInit 

[in]
A pointer to an opaque structure containing
        initialization information.  This structure is managed by UCX.


#### - Endpoint [in]

A handle to a UCXENDPOINT object that represents the endpoint.

## -returns

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.

## -remarks

The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a>
 method.

This callback function creates a UCX static streams object by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxsstreams/nf-ucxsstreams-ucxstaticstreamscreate">UcxStaticStreamsCreate</a>
 method. Only one UCX static streams object can be associated with a single endpoint.  The driver then calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxsstreams/nf-ucxsstreams-ucxstaticstreamssetstreaminfo">UcxStaticStreamsSetStreamInfo</a>
 once per stream to create a queue for each stream.

A static streams object is not enabled
    until UCX calls the client driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nc-ucxendpoint-evt_ucx_endpoint_static_streams_enable">EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE</a> callback function.


#### Examples


```cpp
NTSTATUS
Endpoint_EvtEndpointStaticStreamsAdd(
    UCXENDPOINT         UcxEndpoint,
    ULONG               NumberOfStreams,
    PUCXSSTREAMS_INIT   UcxStaticStreamsInit
    )
{
    NTSTATUS                    status;
    WDF_OBJECT_ATTRIBUTES       wdfAttributes;
    UCXSSTREAMS                 ucxStaticStreams;
    STREAM_INFO                 streamInfo;
    ULONG                       streamId;

    TRY {

        WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&wdfAttributes, STATIC_STREAMS_CONTEXT);

        status = UcxStaticStreamsCreate(UcxEndpoint,
                                        &UcxStaticStreamsInit,
                                        &wdfAttributes,
                                        &ucxStaticStreams);
        // … error handling …

        for (i = 0, streamId = 1; i < NumberOfStreams; i += 1, streamId += 1) {

            // … create WDF queue …

            STREAM_INFO_INIT(&streamInfo,
                             wdfQueue,
                             streamId);

            UcxStaticStreamsSetStreamInfo(ucxStaticStreams, &streamInfo);
        }

```


