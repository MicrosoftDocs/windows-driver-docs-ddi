---
UID: NE:ucxendpoint._ENDPOINT_RESET_FLAGS
title: _ENDPOINT_RESET_FLAGS
author: windows-driver-content
description: Defines parameters for a request to reset an endpoint.
old-location: buses\endpoint_reset_flags.htm
old-project: usbref
ms.assetid: 3775836D-DC1E-47B4-8186-2AC329825FCE
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ENDPOINT_RESET_FLAGS, ucxendpoint/ENDPOINT_RESET_FLAGS, _ENDPOINT_RESET_FLAGS, ucxendpoint/FlagEndpointResetPreserveTransferState, ENDPOINT_RESET_FLAGS enumeration [Buses], buses.endpoint_reset_flags, FlagEndpointResetPreserveTransferState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	ucxendpoint.h
apiname: 
-	ENDPOINT_RESET_FLAGS
product: Windows
targetos: Windows
req.typenames: ENDPOINT_RESET_FLAGS
req.product: Windows 10 or later.
---

# _ENDPOINT_RESET_FLAGS enumeration


## -description


Defines parameters for a request to reset an endpoint.


## -syntax


````
typedef enum _ENDPOINT_RESET_FLAGS { 
  FlagEndpointResetPreserveTransferState  = 0x1
} ENDPOINT_RESET_FLAGS;
````


## -enum-fields




### -field FlagEndpointResetPreserveTransferState

The transfer state must be preserved after the endpoint reset operation is complete.


## -see-also

<a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_reset.md">EVT_UCX_ENDPOINT_RESET</a>

<a href="..\ucxendpoint\ns-ucxendpoint-_endpoint_reset.md">ENDPOINT_RESET</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20ENDPOINT_RESET_FLAGS enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

