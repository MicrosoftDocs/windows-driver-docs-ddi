---
UID: NF:ucxendpoint.UCX_ENDPOINT_EVENT_CALLBACKS_INIT
title: UCX_ENDPOINT_EVENT_CALLBACKS_INIT function
author: windows-driver-content
description: Initializes a UCX_ENDPOINT_EVENT_CALLBACKS structure with client driver's callback functions. The client driver calls this function before calling UcxEndpointCreate method to create an endpoint and register its callback functions with UCX.
old-location: buses\_ucx_endpoint_event_callbacks_init.htm
old-project: usbref
ms.assetid: 1890052A-EE98-4749-ACF9-8321148F3828
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ucxendpoint/UCX_ENDPOINT_EVENT_CALLBACKS_INIT, buses._ucx_endpoint_event_callbacks_init, UCX_ENDPOINT_EVENT_CALLBACKS_INIT, UCX_ENDPOINT_EVENT_CALLBACKS_INIT function [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucxendpoint.h
req.include-header: Ucxclass.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ucxendpoint.h
apiname:
-	UCX_ENDPOINT_EVENT_CALLBACKS_INIT
product: Windows
targetos: Windows
req.typenames: UCX_ENDPOINT_CHARACTERISTIC_TYPE
req.product: Windows 10 or later.
---

# UCX_ENDPOINT_EVENT_CALLBACKS_INIT function


## -description


Initializes a <a href="..\ucxendpoint\ns-ucxendpoint-_ucx_endpoint_event_callbacks.md">UCX_ENDPOINT_EVENT_CALLBACKS</a> structure with client driver's callback functions. The client driver calls this function before calling <a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a> method to create an endpoint and register its callback functions with UCX.


## -syntax


````
void UCX_ENDPOINT_EVENT_CALLBACKS_INIT(
  _Out_ PUCX_ENDPOINT_EVENT_CALLBACKS                Callbacks,
  _In_  PEVT_UCX_ENDPOINT_PURGE                      EvtEndpointPurge,
  _In_  PEVT_UCX_ENDPOINT_START                      EvtEndpointStart,
  _In_  PEVT_UCX_ENDPOINT_ABORT                      EvtEndpointAbort,
  _In_  PEVT_UCX_ENDPOINT_RESET                      EvtEndpointReset,
  _In_  PEVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS     EvtEndpointOkToCancelTransfers,
  _In_  PEVT_UCX_ENDPOINT_STATIC_STREAMS_ADD         EvtEndpointStaticStreamsAdd,
  _In_  PEVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE      EvtEndpointStaticStreamsEnable,
  _In_  PEVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE     EvtEndpointStaticStreamsDisable
);
````


## -parameters




### -param Callbacks [out]

A pointer to a <a href="..\ucxendpoint\ns-ucxendpoint-_ucx_endpoint_event_callbacks.md">UCX_ENDPOINT_EVENT_CALLBACKS</a> structure that contains pointers to the client driver's event callback functions.


### -param EvtEndpointPurge [in]

A pointer to client driver's implementation of the <a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_purge.md">EVT_UCX_ENDPOINT_PURGE</a>                     event callback function.


### -param EvtEndpointStart [in]

A pointer to client driver's implementation of the <a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_start.md">EVT_UCX_ENDPOINT_START</a>                     event callback function.


### -param EvtEndpointAbort [in]

A pointer to client driver's implementation of the <a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_abort.md">EVT_UCX_ENDPOINT_ABORT</a>                     event callback function.


### -param EvtEndpointReset [in]

A pointer to client driver's implementation of the <a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_reset.md">EVT_UCX_ENDPOINT_RESET</a>                     event callback function.


### -param EvtEndpointOkToCancelTransfers [in]

A pointer to client driver's implementation of the <a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_ok_to_cancel_transfers.md">EVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS</a>    event callback function.


### -param EvtEndpointStaticStreamsAdd [in]

A pointer to client driver's implementation of the <a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_static_streams_add.md">EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD</a>        event callback function.


### -param EvtEndpointStaticStreamsEnable [in]

A pointer to client driver's implementation of the <a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_static_streams_enable.md">EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE</a>     event callback function.


### -param EvtEndpointStaticStreamsDisable [in]

A pointer to client driver's implementation of the <a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_static_streams_disable.md">EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE</a>    event callback function.


## -returns


This function does not return a value.



## -see-also

<a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCX_ENDPOINT_EVENT_CALLBACKS_INIT function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

