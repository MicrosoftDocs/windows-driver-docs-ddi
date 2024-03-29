---
UID: NF:ucxsstreams.UcxStaticStreamsCreate
title: UcxStaticStreamsCreate function (ucxsstreams.h)
description: Creates a static streams object.
old-location: buses\_ucxstaticstreamscreate.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UcxStaticStreamsCreate function"]
ms.keywords: UcxStaticStreamsCreate, UcxStaticStreamsCreate method [Buses], buses._ucxstaticstreamscreate, ucxsstreams/UcxStaticStreamsCreate
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - UcxStaticStreamsCreate
 - ucxsstreams/UcxStaticStreamsCreate
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ucxsstreams.h
api_name:
 - UcxStaticStreamsCreate
---

# UcxStaticStreamsCreate function


## -description

Creates a static streams object.

## -parameters

### -param Endpoint [in]


A handle to the endpoint object that supports static streams. The client driver retrieved the handle in a previous call to <a href="/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a>.

### -param StaticStreamsInit

<p>A pointer to a <b>UCXSSTREAMS_INIT</b> structure that describes various configuration
        operations for creating the stream object. The driver specifies function pointers to its callback functions in this structure.
    This structure is managed by UCX.</p>

### -param Attributes [in, optional]


A pointer to a caller-allocated <a href="/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that specifies attributes for the stream object.

### -param StaticStreams

<p>A pointer to a variable that receives a handle to the new stream object.</p>

## -returns

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.

## -remarks

The client driver for the host controller must call this method after the <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a> call. The parent of the new endpoint object is the endpoint object. 

Typically, the client driver calls this method in its implementation of the <a href="/windows-hardware/drivers/ddi/ucxusbdevice/nc-ucxusbdevice-evt_ucx_usbdevice_endpoint_add">EVT_UCX_USBDEVICE_ENDPOINT_ADD</a> event callback.
