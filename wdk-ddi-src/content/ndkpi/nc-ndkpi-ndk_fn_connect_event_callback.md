---
UID: NC:ndkpi.NDK_FN_CONNECT_EVENT_CALLBACK
title: NDK_FN_CONNECT_EVENT_CALLBACK (ndkpi.h)
description: The NdkConnectEventCallback (NDK_FN_CONNECT_EVENT_CALLBACK) function is called by an NDK provider to notify a consumer about an incoming connection request.
old-location: netvista\ndk_fn_connect_event_callback.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDK_FN_CONNECT_EVENT_CALLBACK callback function"]
ms.keywords: NDK_FN_CONNECT_EVENT_CALLBACK, NDK_FN_CONNECT_EVENT_CALLBACK callback, NdkConnectEventCallback, NdkConnectEventCallback callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkConnectEventCallback, netvista.ndk_fn_connect_event_callback
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NDK_FN_CONNECT_EVENT_CALLBACK
 - ndkpi/NDK_FN_CONNECT_EVENT_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ndkpi.h
api_name:
 - NdkConnectEventCallback
---

# NDK_FN_CONNECT_EVENT_CALLBACK callback function


## -description

The <i>NdkConnectEventCallback</i> (<i>NDK_FN_CONNECT_EVENT_CALLBACK</i>) function is called by an NDK provider to notify a consumer about an incoming connection request.

## -parameters

### -param ConnectEventContext 

[in, optional]
A context area that was specified in the <i>ConnectEventContext</i> parameter of the <i>NdkCreateListener</i> (<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_listener">NDK_FN_CREATE_LISTENER</a>) function when the listener object was created.

### -param pNdkConnector 

[in]
A pointer to an NDK connector object (<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector">NDK_CONNECTOR</a>) that represents a new incoming connection request.

## -remarks

<div class="alert"><b>Note</b>  This function is implemented by the NDK consumer and passed to the NDK provider.</div>
<div> </div>
The NDK consumer specified the <i>NdkConnectEventCallback</i> function  in the <i>ConnectEventContext</i> parameter of the <i>NdkCreateListener</i> (<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_listener">NDK_FN_CREATE_LISTENER</a>) function when the listener object was created.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector">NDK_CONNECTOR</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_listener">NDK_FN_CREATE_LISTENER</a>
