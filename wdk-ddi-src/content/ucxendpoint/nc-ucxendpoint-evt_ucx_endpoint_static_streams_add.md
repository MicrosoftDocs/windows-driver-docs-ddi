---
UID: NC:ucxendpoint.EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD
title: EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD
author: windows-driver-content
description: The client driver's implementation that UCX calls to create static streams.
old-location: buses\evt_ucx_endpoint_static_streams_add.htm
old-project: usbref
ms.assetid: 76f94f19-894a-47af-a407-8e14263f1143
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD, EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD callback, EvtUcxEndpointStaticStreamsAdd, EvtUcxEndpointStaticStreamsAdd callback function [Buses], PEVT_UCX_ENDPOINT_STATIC_STREAMS_ADD, PEVT_UCX_ENDPOINT_STATIC_STREAMS_ADD callback function pointer [Buses], buses.evt_ucx_endpoint_static_streams_add, ucxendpoint/EvtUcxEndpointStaticStreamsAdd
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ucxendpoint.h
api_name:
-	PEVT_UCX_ENDPOINT_STATIC_STREAMS_ADD
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD callback function


## -description


The client driver's implementation that UCX calls to create static streams.


## -parameters




### -param UcxEndpoint


### -param NumberOfStreams [in]

The number of non-default streams to create.


### -param UcxStaticStreamsInit [in]

A pointer to an opaque structure containing
        initialization information.  This structure is managed by UCX.


#### - Endpoint [in]

A handle to a UCXENDPOINT object that represents the endpoint.


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.




## -remarks



The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a>
 method.

This callback function creates a UCX static streams object by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188050">UcxStaticStreamsCreate</a>
 method. Only one UCX static streams object can be associated with a single endpoint.  The driver then calls <a href="https://msdn.microsoft.com/library/windows/hardware/mt188051">UcxStaticStreamsSetStreamInfo</a>
 once per stream to create a queue for each stream.

A static streams object is not enabled
    until UCX calls the client driver's <a href="https://msdn.microsoft.com/library/windows/hardware/mt187832">EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE</a> callback function.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
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

        WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&amp;wdfAttributes, STATIC_STREAMS_CONTEXT);

        status = UcxStaticStreamsCreate(UcxEndpoint,
                                        &amp;UcxStaticStreamsInit,
                                        &amp;wdfAttributes,
                                        &amp;ucxStaticStreams);
        // … error handling …

        for (i = 0, streamId = 1; i &lt; NumberOfStreams; i += 1, streamId += 1) {

            // … create WDF queue …

            STREAM_INFO_INIT(&amp;streamInfo,
                             wdfQueue,
                             streamId);

            UcxStaticStreamsSetStreamInfo(ucxStaticStreams, &amp;streamInfo);
        }
</pre>
</td>
</tr>
</table></span></div>


