---
UID: NC:ndisndk.CLOSE_NDK_ADAPTER_HANDLER
title: CLOSE_NDK_ADAPTER_HANDLER
author: windows-driver-content
description: The CloseNDKAdapterHandler (CLOSE_NDK_ADAPTER_HANDLER) function closes an NDK adapter instance on an NDK-capable NDIS miniport adapter.
old-location: netvista\close_ndk_adapter_handler.htm
old-project: netvista
ms.assetid: 9D5980F1-A244-4C5C-B032-68C10BF9D6E7
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.close_ndk_adapter_handler, CloseNdkAdapterHandler callback function [Network Drivers Starting with Windows Vista], CloseNdkAdapterHandler, CLOSE_NDK_ADAPTER_HANDLER, CLOSE_NDK_ADAPTER_HANDLER, ndisndk/CloseNdkAdapterHandler
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndisndk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: None supported
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ndisndk.h
apiname:
-	CloseNdkAdapterHandler
product: Windows
targetos: Windows
req.typenames: TCP_OFFLOAD_STATS, *PTCP_OFFLOAD_STATS
---

# CLOSE_NDK_ADAPTER_HANDLER callback


## -description


The <i>CloseNDKAdapterHandler</i> (<i>CLOSE_NDK_ADAPTER_HANDLER</i>) function closes an NDK adapter instance on an NDK-capable NDIS miniport adapter.


## -prototype


````
CLOSE_NDK_ADAPTER_HANDLER CloseNdkAdapterHandler;

VOID CloseNdkAdapterHandler(
  _In_ NDIS_HANDLE MiniportAdapterContext,
  _In_ NDK_ADAPTER *pNdkAdapter
)
{ ... }
````


## -parameters




#### - MiniportAdapterContext [in]

A handle to a context area that the miniport driver allocated in its <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function. The miniport driver uses this context area to maintain state information for an NDIS  miniport adapter.


#### - *pNdkAdapter [in]

A pointer to the <a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER</a> instance to close.


#### - pNdkAdapter [in]

A pointer to the <a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER</a> instance to close.


## -returns


None



## -remarks


The <i>CLOSE_NDK_ADAPTER_HANDLER</i> function closes an <a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER</a> instance on an NDK-capable NDIS miniport adapter.
 The miniport driver previously opened the  NDK_ADAPTER instance by calling the <a href="..\ndisndk\nc-ndisndk-open_ndk_adapter_handler.md">OPEN_NDK_ADAPTER_HANDLER</a> function.



## -see-also

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER</a>

<a href="..\ndisndk\nc-ndisndk-open_ndk_adapter_handler.md">OPEN_NDK_ADAPTER_HANDLER</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_adapter_dispatch.md">NDK_ADAPTER_DISPATCH</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20CLOSE_NDK_ADAPTER_HANDLER callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

