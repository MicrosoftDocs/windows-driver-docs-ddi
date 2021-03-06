---
UID: NS:ndkpi._NDK_CONNECTOR_DISPATCH
title: _NDK_CONNECTOR_DISPATCH (ndkpi.h)
description: The NDK_CONNECTOR_DISPATCH structure specifies dispatch function entry points for the NDK connector object.
old-location: netvista\ndk_connector_dispatch.htm
tech.root: netvista
ms.date: 12/20/2020
keywords: ["NDK_CONNECTOR_DISPATCH structure"]
ms.keywords: NDK_CONNECTOR_DISPATCH, NDK_CONNECTOR_DISPATCH structure [Network Drivers Starting with Windows Vista], PNDK_CONNECTOR_DISPATCH, PNDK_CONNECTOR_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], _NDK_CONNECTOR_DISPATCH, ndkpi/NDK_CONNECTOR_DISPATCH, ndkpi/PNDK_CONNECTOR_DISPATCH, netvista.ndk_connector_dispatch
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
targetos: Windows
req.typenames: NDK_CONNECTOR_DISPATCH
f1_keywords:
 - _NDK_CONNECTOR_DISPATCH
 - ndkpi/_NDK_CONNECTOR_DISPATCH
 - NDK_CONNECTOR_DISPATCH
 - ndkpi/NDK_CONNECTOR_DISPATCH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndkpi.h
api_name:
 - _NDK_CONNECTOR_DISPATCH
 - NDK_CONNECTOR_DISPATCH
---

# _NDK_CONNECTOR_DISPATCH structure


## -description

The <b>NDK_CONNECTOR_DISPATCH</b> structure specifies dispatch function entry points for the NDK connector object.

## -struct-fields

### -field NdkCloseConnector

The entry point for the object's <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_close_object">NDK_FN_CLOSE_OBJECT</a> dispatch function.

### -field NdkQueryExtension

The entry point for the object's <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_query_extension_interface">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.

### -field NdkConnect

The entry point for the object's <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_connect">NDK_FN_CONNECT</a> dispatch function.

### -field NdkConnectWithSharedEndpoint

The entry point for the object's <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_connect_with_shared_endpoint">NDK_FN_CONNECT_WITH_SHARED_ENDPOINT</a> dispatch function.

### -field NdkCompleteConnect

The entry point for the object's <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_complete_connect">NDK_FN_COMPLETE_CONNECT</a> dispatch function.

### -field NdkAccept

The entry point for the object's <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_accept">NDK_FN_ACCEPT</a> dispatch function.

### -field NdkReject

The entry point for the object's <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_reject">NDK_FN_REJECT</a> dispatch function.

### -field NdkGetConnectionData

The entry point for the object's <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_connection_data">NDK_FN_GET_CONNECTION_DATA</a> dispatch function.

### -field NdkGetLocalAddress

The entry point for the object's <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_local_address">NDK_FN_GET_LOCAL_ADDRESS</a> dispatch function.

### -field NdkGetPeerAddress

The entry point for the object's <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_peer_address">NDK_FN_GET_PEER_ADDRESS</a> dispatch function.

### -field NdkDisconnect

The entry point for the object's <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_disconnect">NDK_FN_DISCONNECT</a> dispatch function.

### -field NdkCompleteConnectEx

The entry point for the object's [NDK_FN_COMPLETE_CONNECT_EX](nc-ndkpi-ndk_fn_complete_connect_ex.md) dispatch function.

### -field NdkAcceptEx

The entry point for the object's [NDK_FN_ACCEPT_EX](nc-ndkpi-ndk_fn_accept_ex.md) dispatch function.

## -remarks

The <b>NDK_CONNECTOR_DISPATCH</b> structure is used in the <a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector">NDK_CONNECTOR</a> structure.

## -see-also

[NDK_FN_ACCEPT_EX](nc-ndkpi-ndk_fn_accept_ex.md)

[NDK_FN_COMPLETE_CONNECT_EX](nc-ndkpi-ndk_fn_complete_connect_ex.md)

[NDK_CONNECTOR](./ns-ndkpi-_ndk_connector.md)



[NDK_FN_ACCEPT](./nc-ndkpi-ndk_fn_accept.md)



[NDK_FN_CLOSE_OBJECT](./nc-ndkpi-ndk_fn_close_object.md)



[NDK_FN_COMPLETE_CONNECT](./nc-ndkpi-ndk_fn_complete_connect.md)



[NDK_FN_CONNECT](./nc-ndkpi-ndk_fn_connect.md)



[NDK_FN_CONNECT_WITH_SHARED_ENDPOINT](./nc-ndkpi-ndk_fn_connect_with_shared_endpoint.md)



[NDK_FN_DISCONNECT](./nc-ndkpi-ndk_fn_disconnect.md)



[NDK_FN_GET_CONNECTION_DATA](./nc-ndkpi-ndk_fn_get_connection_data.md)



[NDK_FN_GET_LOCAL_ADDRESS](./nc-ndkpi-ndk_fn_get_local_address.md)



[NDK_FN_GET_PEER_ADDRESS](./nc-ndkpi-ndk_fn_get_peer_address.md)



[NDK_FN_QUERY_EXTENSION_INTERFACE](./nc-ndkpi-ndk_fn_query_extension_interface.md)



[NDK_FN_REJECT](./nc-ndkpi-ndk_fn_reject.md)