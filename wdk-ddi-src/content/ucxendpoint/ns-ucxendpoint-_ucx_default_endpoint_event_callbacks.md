---
UID: NS:ucxendpoint._UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS
title: "_UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS"
author: windows-driver-content
description: This structure provides a list of UCX default endpoint event callback functions.
old-location: buses\_ucx_default_endpoint_event_callbacks.htm
old-project: usbref
ms.assetid: A22E96FC-E219-4F6C-B8AF-AC86FAD89543
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS, P_UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS, P_UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS structure pointer [Buses], UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS, UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS structure [Buses], _UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS, buses._ucx_default_endpoint_event_callbacks, ucxendpoint/P_UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS, ucxendpoint/_UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxendpoint.h
req.include-header: Ucxclass.h, Ucxendpoint.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucxendpoint.h
api_name:
-	UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS
product: Windows
targetos: Windows
req.typenames: UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS, *PUCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS
req.product: Windows 10 or later.
---

# _UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS structure


## -description


This structure provides a list of UCX default endpoint event callback functions.


## -struct-fields




### -field Size

The size in bytes of this structure.


### -field EvtEndpointPurge

A pointer to a EVT_UCX_ENDPOINT_PURGE callback function.


### -field EvtEndpointStart

A pointer to a EVT_UCX_ENDPOINT_START callback function.


### -field EvtEndpointAbort

A pointer to a EVT_UCX_ENDPOINT_ABORT callback function.


### -field EvtEndpointOkToCancelTransfers

A pointer to a EVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS callback function.


### -field EvtDefaultEndpointUpdate

A pointer to a EVT_UCX_DEFAULT_ENDPOINT_UPDATE callback function.


### -field Reserved1

Do not use.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187950">UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188037">UcxDefaultEndpointInitSetEventCallbacks</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

