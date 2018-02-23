---
UID: NF:ucxendpoint.UcxEndpointNoPingResponseError
title: UcxEndpointNoPingResponseError function
author: windows-driver-content
description: Notifies UCX about a &#0034;No Ping Response&#0034; error for a transfer on the specified endpoint object.
old-location: buses\_ucxendpointnopingresponseerror.htm
old-project: UsbRef
ms.assetid: 0EDC524E-12BB-49AD-AA12-A7D9CF7D2F9C
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: UcxEndpointNoPingResponseError method [Buses], ucxendpoint/UcxEndpointNoPingResponseError, UcxEndpointNoPingResponseError, buses._ucxendpointnopingresponseerror
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucxendpoint.h
req.include-header: Ucxclass.h, Ucxendpoint.h
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ucxendpoint.h
apiname:
-	UcxEndpointNoPingResponseError
product: Windows
targetos: Windows
req.typenames: UCX_ENDPOINT_CHARACTERISTIC_TYPE
req.product: Windows 10 or later.
---

# UcxEndpointNoPingResponseError function


## -description


Notifies UCX about a "No Ping Response" error for a transfer on
    the specified endpoint object


## -syntax


````
void UcxEndpointNoPingResponseError(
  [in] UCXENDPOINT Endpoint
);
````


## -parameters




### -param Endpoint [in]

A handle to the endpoint object. The client driver retrieved the handle in a previous call to <a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a>.


## -returns



This method does not return a value.




## -see-also

<a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UcxEndpointNoPingResponseError method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

