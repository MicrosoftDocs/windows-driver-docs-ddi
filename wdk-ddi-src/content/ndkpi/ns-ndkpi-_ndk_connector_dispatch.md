---
UID: NS:ndkpi._NDK_CONNECTOR_DISPATCH
title: "_NDK_CONNECTOR_DISPATCH"
author: windows-driver-content
description: The NDK_CONNECTOR_DISPATCH structure specifies dispatch function entry points for the NDK connector object.
old-location: netvista\ndk_connector_dispatch.htm
tech.root: netvista
ms.assetid: BBC24A32-4CB6-47AB-BD1D-298159EC9919
ms.date: 05/02/2018
ms.keywords: NDK_CONNECTOR_DISPATCH, NDK_CONNECTOR_DISPATCH structure [Network Drivers Starting with Windows Vista], PNDK_CONNECTOR_DISPATCH, PNDK_CONNECTOR_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], _NDK_CONNECTOR_DISPATCH, ndkpi/NDK_CONNECTOR_DISPATCH, ndkpi/PNDK_CONNECTOR_DISPATCH, netvista.ndk_connector_dispatch
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndkpi.h
api_name:
-	NDK_CONNECTOR_DISPATCH
product:
- Windows
targetos: Windows
req.typenames: NDK_CONNECTOR_DISPATCH
---

# _NDK_CONNECTOR_DISPATCH structure


## -description


The <b>NDK_CONNECTOR_DISPATCH</b> structure specifies dispatch function entry points for the NDK connector object.


## -struct-fields




### -field NdkCloseConnector

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439863">NDK_FN_CLOSE_OBJECT</a> dispatch function.


### -field NdkQueryExtension

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439905">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.


### -field NdkConnect

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439865">NDK_FN_CONNECT</a> dispatch function.


### -field NdkConnectWithSharedEndpoint

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439868">NDK_FN_CONNECT_WITH_SHARED_ENDPOINT</a> dispatch function.


### -field NdkCompleteConnect

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439864">NDK_FN_COMPLETE_CONNECT</a> dispatch function.


### -field NdkAccept

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439857">NDK_FN_ACCEPT</a> dispatch function.


### -field NdkReject

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439909">NDK_FN_REJECT</a> dispatch function.


### -field NdkGetConnectionData

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439890">NDK_FN_GET_CONNECTION_DATA</a> dispatch function.


### -field NdkGetLocalAddress

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439893">NDK_FN_GET_LOCAL_ADDRESS</a> dispatch function.


### -field NdkGetPeerAddress

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439895">NDK_FN_GET_PEER_ADDRESS</a> dispatch function.


### -field NdkDisconnect

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439885">NDK_FN_DISCONNECT</a> dispatch function.


## -remarks



The <b>NDK_CONNECTOR_DISPATCH</b> structure is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439852">NDK_CONNECTOR</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439852">NDK_CONNECTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439857">NDK_FN_ACCEPT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439863">NDK_FN_CLOSE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439864">NDK_FN_COMPLETE_CONNECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439865">NDK_FN_CONNECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439868">NDK_FN_CONNECT_WITH_SHARED_ENDPOINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439885">NDK_FN_DISCONNECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439890">NDK_FN_GET_CONNECTION_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439893">NDK_FN_GET_LOCAL_ADDRESS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439895">NDK_FN_GET_PEER_ADDRESS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439905">NDK_FN_QUERY_EXTENSION_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439909">NDK_FN_REJECT</a>
 

 

