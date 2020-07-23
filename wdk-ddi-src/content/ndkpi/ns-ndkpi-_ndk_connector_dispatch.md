---
UID: NS:ndkpi._NDK_CONNECTOR_DISPATCH
title: _NDK_CONNECTOR_DISPATCH (ndkpi.h)
description: The NDK_CONNECTOR_DISPATCH structure specifies dispatch function entry points for the NDK connector object.
old-location: netvista\ndk_connector_dispatch.htm
tech.root: netvista
ms.assetid: BBC24A32-4CB6-47AB-BD1D-298159EC9919
ms.date: 05/02/2018
keywords: ["_NDK_CONNECTOR_DISPATCH structure"]
ms.keywords: NDK_CONNECTOR_DISPATCH, NDK_CONNECTOR_DISPATCH structure [Network Drivers Starting with Windows Vista], PNDK_CONNECTOR_DISPATCH, PNDK_CONNECTOR_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], _NDK_CONNECTOR_DISPATCH, ndkpi/NDK_CONNECTOR_DISPATCH, ndkpi/PNDK_CONNECTOR_DISPATCH, netvista.ndk_connector_dispatch
f1_keywords:
 - "ndkpi/NDK_CONNECTOR_DISPATCH"
 - "NDK_CONNECTOR_DISPATCH"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndkpi.h
api_name:
- NDK_CONNECTOR_DISPATCH
targetos: Windows
req.typenames: NDK_CONNECTOR_DISPATCH
---

# _NDK_CONNECTOR_DISPATCH structure


## -description


The <b>NDK_CONNECTOR_DISPATCH</b> structure specifies dispatch function entry points for the NDK connector object.


## -struct-fields




### -field NdkCloseConnector

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_close_object">NDK_FN_CLOSE_OBJECT</a> dispatch function.


### -field NdkQueryExtension

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_query_extension_interface">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.


### -field NdkConnect

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_connect">NDK_FN_CONNECT</a> dispatch function.


### -field NdkConnectWithSharedEndpoint

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_connect_with_shared_endpoint">NDK_FN_CONNECT_WITH_SHARED_ENDPOINT</a> dispatch function.


### -field NdkCompleteConnect

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_complete_connect">NDK_FN_COMPLETE_CONNECT</a> dispatch function.


### -field NdkAccept

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_accept">NDK_FN_ACCEPT</a> dispatch function.


### -field NdkReject

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_reject">NDK_FN_REJECT</a> dispatch function.


### -field NdkGetConnectionData

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_connection_data">NDK_FN_GET_CONNECTION_DATA</a> dispatch function.


### -field NdkGetLocalAddress

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_local_address">NDK_FN_GET_LOCAL_ADDRESS</a> dispatch function.


### -field NdkGetPeerAddress

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_peer_address">NDK_FN_GET_PEER_ADDRESS</a> dispatch function.


### -field NdkDisconnect

The entry point for the object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_disconnect">NDK_FN_DISCONNECT</a> dispatch function.


## -remarks



The <b>NDK_CONNECTOR_DISPATCH</b> structure is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector">NDK_CONNECTOR</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector">NDK_CONNECTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_accept">NDK_FN_ACCEPT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_close_object">NDK_FN_CLOSE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_complete_connect">NDK_FN_COMPLETE_CONNECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_connect">NDK_FN_CONNECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_connect_with_shared_endpoint">NDK_FN_CONNECT_WITH_SHARED_ENDPOINT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_disconnect">NDK_FN_DISCONNECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_connection_data">NDK_FN_GET_CONNECTION_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_local_address">NDK_FN_GET_LOCAL_ADDRESS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_peer_address">NDK_FN_GET_PEER_ADDRESS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_query_extension_interface">NDK_FN_QUERY_EXTENSION_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_reject">NDK_FN_REJECT</a>
 

 

