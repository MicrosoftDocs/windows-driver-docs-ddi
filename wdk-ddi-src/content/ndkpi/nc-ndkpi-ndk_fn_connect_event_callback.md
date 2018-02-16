---
UID: NC:ndkpi.NDK_FN_CONNECT_EVENT_CALLBACK
title: NDK_FN_CONNECT_EVENT_CALLBACK
author: windows-driver-content
description: The NdkConnectEventCallback (NDK_FN_CONNECT_EVENT_CALLBACK) function is called by an NDK provider to notify a consumer about an incoming connection request.
old-location: netvista\ndk_fn_connect_event_callback.htm
old-project: netvista
ms.assetid: D7009707-7139-4572-A620-C8ACFA6B5665
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndk_fn_connect_event_callback, NdkConnectEventCallback callback function [Network Drivers Starting with Windows Vista], NdkConnectEventCallback, NDK_FN_CONNECT_EVENT_CALLBACK, NDK_FN_CONNECT_EVENT_CALLBACK, ndkpi/NdkConnectEventCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ndkpi.h
apiname:
-	NdkConnectEventCallback
product: Windows
targetos: Windows
req.typenames: "*PNDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS"
---

# NDK_FN_CONNECT_EVENT_CALLBACK callback


## -description


The <i>NdkConnectEventCallback</i> (<i>NDK_FN_CONNECT_EVENT_CALLBACK</i>) function is called by an NDK provider to notify a consumer about an incoming connection request.



## -prototype


````
NDK_FN_CONNECT_EVENT_CALLBACK NdkConnectEventCallback;

VOID NdkConnectEventCallback(
  _In_opt_ PVOID         ConnectEventContext,
  _In_     NDK_CONNECTOR *pNdkConnector
)
{ ... }
````


## -parameters




### -param ConnectEventContext [in, optional]

A context area that was specified in the <i>ConnectEventContext</i> parameter of the <i>NdkCreateListener</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_listener.md">NDK_FN_CREATE_LISTENER</a>) function when the listener object was created.


### -param *pNdkConnector [in]

A pointer to an NDK connector object (<a href="..\ndkpi\ns-ndkpi-_ndk_connector.md">NDK_CONNECTOR</a>) that represents a new incoming connection request.


## -returns



None




## -remarks



<div class="alert"><b>Note</b>  This function is implemented by the NDK consumer and passed to the NDK provider.</div>
<div> </div>
The NDK consumer specified the <i>NdkConnectEventCallback</i> function  in the <i>ConnectEventContext</i> parameter of the <i>NdkCreateListener</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_listener.md">NDK_FN_CREATE_LISTENER</a>) function when the listener object was created.




## -see-also

<a href="..\ndkpi\ns-ndkpi-_ndk_connector.md">NDK_CONNECTOR</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_listener.md">NDK_FN_CREATE_LISTENER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_CONNECT_EVENT_CALLBACK callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

