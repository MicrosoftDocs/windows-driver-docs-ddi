---
UID: NF:ucxendpoint.UcxEndpointGetStaticStreamsReferenced
title: UcxEndpointGetStaticStreamsReferenced function
author: windows-driver-content
description: Returns a referenced static streams object for the specified endpoint.
old-location: buses\_ucxendpointgetstaticstreamsreferenced.htm
old-project: usbref
ms.assetid: A9AB43A9-1409-4AA4-99DE-66D558F2303C
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UcxEndpointGetStaticStreamsReferenced method [Buses], ucxendpoint/UcxEndpointGetStaticStreamsReferenced, buses._ucxendpointgetstaticstreamsreferenced, UcxEndpointGetStaticStreamsReferenced
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
req.irql: <=DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	COM
apilocation: 
-	ucxendpoint.h
apiname: 
-	UcxEndpointGetStaticStreamsReferenced
product: Windows
targetos: Windows
req.typenames: UCX_ENDPOINT_CHARACTERISTIC_TYPE
req.product: Windows 10 or later.
---

# UcxEndpointGetStaticStreamsReferenced function


## -description


Returns a referenced static streams object for the specified endpoint.


## -syntax


````
UCXSSTREAMS UcxEndpointGetStaticStreamsReferenced(
  [in] UCXENDPOINT Endpoint,
  [in] PVOID       Tag
);
````


## -parameters




### -param Endpoint [in]

A handle to the endpoint object for which the static streams object is requested. The client driver retrieved the handle in a previous call to <a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a>.


### -param Tag [in]

A driver-defined value that the framework stores as an identification tag for the object reference.




## -returns


A handle to the stream object if it is opened with the endpoint. Otherwise, NULL.



## -remarks


The client driver can use this function to determine whether it has created a streams object for this endpoint. If it create the object the method returns the  UCXSSTREAMS handle. The method returns NULL if the object was not created, or if the client driver failed the framework request object passed in the <a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_static_streams_enable.md">EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE</a> callback. Any call to this method must be matched by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548746">WdfObjectDereferenceWithTag</a> by using the same Tag.



## -see-also

<a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcxEndpointGetStaticStreamsReferenced method%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

