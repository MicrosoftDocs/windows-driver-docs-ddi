---
UID: NF:ucxsstreams.UcxStaticStreamsSetStreamInfo
title: UcxStaticStreamsSetStreamInfo function (ucxsstreams.h)
description: Sets stream information for each stream enabled by the client driver.
old-location: buses\_ucxstaticstreamssetstreaminfo.htm
tech.root: usbref
ms.assetid: 40AE9327-ABB7-4A63-AC90-494E2BC26C08
ms.date: 05/07/2018
keywords: ["UcxStaticStreamsSetStreamInfo function"]
ms.keywords: UcxStaticStreamsSetStreamInfo, UcxStaticStreamsSetStreamInfo method [Buses], buses._ucxstaticstreamssetstreaminfo
req.header: ucxsstreams.h
req.include-header: Ucxclass.h, Ucxstreams.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - UcxStaticStreamsSetStreamInfo
 - ucxsstreams/UcxStaticStreamsSetStreamInfo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ucxsstreams.h
api_name:
 - UcxStaticStreamsSetStreamInfo
---

# UcxStaticStreamsSetStreamInfo function


## -description

Sets stream information for each stream enabled by the client driver.

## -parameters

### -param StaticStreams 

[in]
                The handle to the Static Streams object just been created.

### -param StreamInfo 

[in]
                A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxsstreams/ns-ucxsstreams-_stream_info">STREAM_INFO</a> structure that contains static stream-related information.

## -remarks

The client driver must call this method from its implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nc-ucxendpoint-evt_ucx_endpoint_static_streams_add">EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD</a> event callback . 
    This method must be called for the number of streams on the endpoint. 

For a code example, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nc-ucxendpoint-evt_ucx_endpoint_static_streams_add">EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a>

