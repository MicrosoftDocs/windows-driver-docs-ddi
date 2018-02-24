---
UID: NF:ucxsstreams.UcxStaticStreamsCreate
title: UcxStaticStreamsCreate function
author: windows-driver-content
description: Creates a static streams object.
old-location: buses\_ucxstaticstreamscreate.htm
old-project: UsbRef
ms.assetid: F7AA10E3-5F56-4751-A603-54A0BFB00927
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ucxsstreams/UcxStaticStreamsCreate, UcxStaticStreamsCreate method [Buses], UcxStaticStreamsCreate, buses._ucxstaticstreamscreate
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ucxsstreams.h
apiname:
-	UcxStaticStreamsCreate
product: Windows
targetos: Windows
req.typenames: "*PUCX_ROOTHUB_CONFIG, UCX_ROOTHUB_CONFIG"
req.product: Windows 10 or later.
---

# UcxStaticStreamsCreate function


## -description


Creates a static streams object.


## -syntax


````
NTSTATUS UcxStaticStreamsCreate(
  [in]           UCXENDPOINT            Endpoint,
  [out]          PUCXSSTREAMS_INIT      *SStreamsInit,
  [in, optional] PWDF_OBJECT_ATTRIBUTES Attributes,
  [out]          UCXSSTREAMS            *SStreams
);
````


## -parameters




### -param Endpoint [in]

A handle to the endpoint object that supports static streams. The client driver retrieved the handle in a previous call to <a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a>.


### -param StaticStreamsInit

TBD


### -param Attributes [in, optional]

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that specifies attributes for the stream object. 


### -param StaticStreams

TBD




#### - SStreams [out]

A pointer to a variable that receives a handle to the new stream object.


#### - SStreamsInit [out]

A pointer to a <b>UCXSSTREAMS_INIT</b> structure that describes various configuration
        operations for creating the stream object. The driver specifies function pointers to its callback functions in this structure.
    This structure is managed by UCX.


## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 




## -remarks



The client driver for the host controller must call this method after the <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a> call. The parent of the new endpoint object is the endpoint object. 

Typically, the client driver calls this method in its implementation of the <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_endpoint_add.md">EVT_UCX_USBDEVICE_ENDPOINT_ADD</a> event callback. 



