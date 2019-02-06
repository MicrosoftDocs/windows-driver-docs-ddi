---
UID: NF:ucxsstreams.UcxStaticStreamsCreate
title: UcxStaticStreamsCreate function (ucxsstreams.h)
description: Creates a static streams object.
old-location: buses\_ucxstaticstreamscreate.htm
tech.root: usbref
ms.assetid: F7AA10E3-5F56-4751-A603-54A0BFB00927
ms.date: 05/07/2018
ms.keywords: UcxStaticStreamsCreate, UcxStaticStreamsCreate method [Buses], buses._ucxstaticstreamscreate, ucxsstreams/UcxStaticStreamsCreate
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ucxsstreams.h
api_name:
-	UcxStaticStreamsCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcxStaticStreamsCreate function


## -description


Creates a static streams object.


## -parameters




### -param Endpoint [in]

A handle to the endpoint object that supports static streams. The client driver retrieved the handle in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a>.


### -param StaticStreamsInit

<p>A pointer to a <b>UCXSSTREAMS_INIT</b> structure that describes various configuration
        operations for creating the stream object. The driver specifies function pointers to its callback functions in this structure.
    This structure is managed by UCX.</p>


### -param Attributes [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that specifies attributes for the stream object. 


### -param StaticStreams

<p>A pointer to a variable that receives a handle to the new stream object.</p>




## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 




## -remarks



The client driver for the host controller must call this method after the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a> call. The parent of the new endpoint object is the endpoint object. 

Typically, the client driver calls this method in its implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187843">EVT_UCX_USBDEVICE_ENDPOINT_ADD</a> event callback. 



