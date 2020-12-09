---
UID: NC:ndkpi.NDK_FN_DISCONNECT_EVENT_CALLBACK_EX
title: NDK_FN_DISCONNECT_EVENT_CALLBACK_EX
ms.date: 12/30/2020
ms.topic: language-reference
targetos: Windows
description: The NdkDisconnectEventCallbackEx (NDK_FN_DISCONNECT_EVENT_CALLBACK_EX) function is called by the NDK provider once when the peer disconnects.
tech.root: netvista
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndkpi.h
req.idl: 
req.include-header: Ndkpi.h
req.irql: <=DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 21H1. Supported in NDKPI 2.1 and later.
req.target-min-winversvr:
req.target-type: Windows
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - ndkpi.h
api_name:
 - NDK_FN_DISCONNECT_EVENT_CALLBACK_EX
f1_keywords:
 - NDK_FN_DISCONNECT_EVENT_CALLBACK_EX
 - ndkpi/NDK_FN_DISCONNECT_EVENT_CALLBACK_EX
dev_langs:
 - c++
---

## -description

The *NdkDisconnectEventCallbackEx* (*NDK_FN_DISCONNECT_EVENT_CALLBACK_EX*) function is called by the NDK provider once when the peer disconnects.

## -parameters

### -param DisconnectEventContext

[in, optional]
A context area that was specified in the *DisconnectEvent* parameter of the *NdkCompleteConnectEx* ([NDK_FN_COMPLETE_CONNECT_EX](nc-ndkpi-ndk_fn_complete_connect_ex.md)) or *NdkAcceptEx* ([NDK_FN_ACCEPT_EX](nc-ndkpi-ndk_fn_accept_ex.md)) function when the completion queue (CQ) object was created.

### -param ProviderDisconnectReason

[in]
A provider specific code that indicates why the connection has disconnected.

**Zero** indicates the NDK consumer does not support the NDK provider or did not provide a reason.

## -remarks

> [!NOTE]
> This routine is implemented by the NDK consumer and passed to the NDK provider.

*NdkDisconnectEventCallbackEx* is a callback function for connection disconnect events.  A disconnect notification callback function is specified for a connection with the *NdkCompleteConnectEx* ([NDK_FN_COMPLETE_CONNECT_EX](nc-ndkpi-ndk_fn_complete_connect_ex.md)) function on the initiator side and with the *NdkAcceptEx* ([NDK_FN_ACCEPT_EX](nc-ndkpi-ndk_fn_accept_ex.md)) function on the listener side. The NDK provider invokes this callback only once when the peer disconnects. The provider should not flush outstanding work requests when it indicates a disconnect event because of an incoming disconnect request from the peer.

## -see-also

[NDK_FN_COMPLETE_CONNECT_EX](nc-ndkpi-ndk_fn_complete_connect_ex.md)

[NDK_FN_ACCEPT_EX](nc-ndkpi-ndk_fn_accept_ex.md)