---
UID: NC:ndisndk.CLOSE_NDK_ADAPTER_HANDLER
title: CLOSE_NDK_ADAPTER_HANDLER (ndisndk.h)
description: The CloseNDKAdapterHandler (CLOSE_NDK_ADAPTER_HANDLER) function closes an NDK adapter instance on an NDK-capable NDIS miniport adapter.
old-location: netvista\close_ndk_adapter_handler.htm
tech.root: netvista
ms.assetid: 9D5980F1-A244-4C5C-B032-68C10BF9D6E7
ms.date: 05/02/2018
keywords: ["CLOSE_NDK_ADAPTER_HANDLER callback function"]
ms.keywords: CLOSE_NDK_ADAPTER_HANDLER, CLOSE_NDK_ADAPTER_HANDLER callback, CloseNdkAdapterHandler, CloseNdkAdapterHandler callback function [Network Drivers Starting with Windows Vista], ndisndk/CloseNdkAdapterHandler, netvista.close_ndk_adapter_handler
f1_keywords:
 - "ndisndk/CloseNdkAdapterHandler"
 - "CloseNdkAdapterHandler"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ndisndk.h
api_name:
- CloseNdkAdapterHandler
product:
- Windows
targetos: Windows
req.typenames: 
---

# CLOSE_NDK_ADAPTER_HANDLER callback function


## -description


The <i>CloseNDKAdapterHandler</i> (<i>CLOSE_NDK_ADAPTER_HANDLER</i>) function closes an NDK adapter instance on an NDK-capable NDIS miniport adapter.


## -parameters




### -param MiniportAdapterContext [in]

A handle to a context area that the miniport driver allocated in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function. The miniport driver uses this context area to maintain state information for an NDIS  miniport adapter.


### -param pNdkAdapter [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_adapter">NDK_ADAPTER</a> instance to close.


## -remarks



The <i>CLOSE_NDK_ADAPTER_HANDLER</i> function closes an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_adapter">NDK_ADAPTER</a> instance on an NDK-capable NDIS miniport adapter.
 The miniport driver previously opened the  NDK_ADAPTER instance by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndisndk/nc-ndisndk-open_ndk_adapter_handler">OPEN_NDK_ADAPTER_HANDLER</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_adapter">NDK_ADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_adapter_dispatch">NDK_ADAPTER_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndisndk/nc-ndisndk-open_ndk_adapter_handler">OPEN_NDK_ADAPTER_HANDLER</a>
 

 

