---
UID: NF:ucxsstreams.UcxStaticStreamsSetStreamInfo
title: UcxStaticStreamsSetStreamInfo function
description: Sets stream information for each stream enabled by the client driver.
old-location: buses\_ucxstaticstreamssetstreaminfo.htm
tech.root: usbref
ms.assetid: 40AE9327-ABB7-4A63-AC90-494E2BC26C08
ms.date: 05/07/2018
ms.keywords: UcxStaticStreamsSetStreamInfo, UcxStaticStreamsSetStreamInfo method [Buses], buses._ucxstaticstreamssetstreaminfo
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ucxsstreams.h
api_name:
-	UcxStaticStreamsSetStreamInfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcxStaticStreamsSetStreamInfo function


## -description


Sets stream information for each stream enabled by the client driver.


## -parameters




### -param StaticStreams [in]

                The handle to the Static Streams object just been created. 


### -param StreamInfo [in]

                A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt188032">STREAM_INFO</a> structure that contains static stream-related information.


## -returns



This method does not return a value.




## -remarks



The client driver must call this method from its implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187830">EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD</a> event callback . 
    This method must be called for the number of streams on the endpoint. 

For a code example, see <a href="https://msdn.microsoft.com/library/windows/hardware/mt187830">EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a>
 

 

