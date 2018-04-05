---
UID: NC:ndisndk.CLOSE_NDK_ADAPTER_HANDLER
title: CLOSE_NDK_ADAPTER_HANDLER
author: windows-driver-content
description: The CloseNDKAdapterHandler (CLOSE_NDK_ADAPTER_HANDLER) function closes an NDK adapter instance on an NDK-capable NDIS miniport adapter.
old-location: netvista\close_ndk_adapter_handler.htm
old-project: netvista
ms.assetid: 9D5980F1-A244-4C5C-B032-68C10BF9D6E7
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: CLOSE_NDK_ADAPTER_HANDLER, CloseNdkAdapterHandler, CloseNdkAdapterHandler callback function [Network Drivers Starting with Windows Vista], ndisndk/CloseNdkAdapterHandler, netvista.close_ndk_adapter_handler
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ndisndk.h
api_name:
-	CloseNdkAdapterHandler
product:
- Windows
targetos: Windows
req.typenames: TCP_OFFLOAD_STATS, *PTCP_OFFLOAD_STATS
---

# CLOSE_NDK_ADAPTER_HANDLER callback


## -description


The <i>CloseNDKAdapterHandler</i> (<i>CLOSE_NDK_ADAPTER_HANDLER</i>) function closes an NDK adapter instance on an NDK-capable NDIS miniport adapter.


## -parameters




### -param MiniportAdapterContext [in]

A handle to a context area that the miniport driver allocated in its <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function. The miniport driver uses this context area to maintain state information for an NDIS  miniport adapter.


### -param *pNdkAdapter [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439848">NDK_ADAPTER</a> instance to close.


## -returns



None




## -remarks



The <i>CLOSE_NDK_ADAPTER_HANDLER</i> function closes an <a href="https://msdn.microsoft.com/library/windows/hardware/hh439848">NDK_ADAPTER</a> instance on an NDK-capable NDIS miniport adapter.
 The miniport driver previously opened the  NDK_ADAPTER instance by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/hh440105">OPEN_NDK_ADAPTER_HANDLER</a> function.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439848">NDK_ADAPTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439850">NDK_ADAPTER_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh440105">OPEN_NDK_ADAPTER_HANDLER</a>
 

 

