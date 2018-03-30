---
UID: NS:ndkpi._NDK_ADAPTER_DISPATCH
title: "_NDK_ADAPTER_DISPATCH"
author: windows-driver-content
description: The NDK_ADAPTER_DISPATCH structure specifies dispatch function entry points for the NDK adapter object.
old-location: netvista\ndk_adapter_dispatch.htm
old-project: netvista
ms.assetid: 61C425CB-4900-4EB2-8D33-FF235BC03929
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NDK_ADAPTER_DISPATCH, NDK_ADAPTER_DISPATCH structure [Network Drivers Starting with Windows Vista], PNDK_ADAPTER_DISPATCH, PNDK_ADAPTER_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], _NDK_ADAPTER_DISPATCH, ndkpi/NDK_ADAPTER_DISPATCH, ndkpi/PNDK_ADAPTER_DISPATCH, netvista.ndk_adapter_dispatch
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndkpi.h
api_name:
-	NDK_ADAPTER_DISPATCH
product: Windows
targetos: Windows
req.typenames: NDK_ADAPTER_DISPATCH
---

# _NDK_ADAPTER_DISPATCH structure


## -description


The <b>NDK_ADAPTER_DISPATCH</b> structure specifies dispatch function entry points for the NDK adapter object.


## -struct-fields




### -field NdkQueryExtension

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439905">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.


### -field NdkQueryAdapterInfo

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439904">NDK_FN_QUERY_ADAPTER_INFO</a> dispatch function.


### -field NdkCreateCq

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439873">NDK_FN_CREATE_CQ</a> dispatch function.


### -field NdkCreatePd

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439877">NDK_FN_CREATE_PD</a> dispatch function.


### -field NdkCreateSharedEndpoint

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439882">NDK_FN_CREATE_SHARED_ENDPOINT</a> dispatch function.


### -field NdkCreateConnector

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439872">NDK_FN_CREATE_CONNECTOR</a> dispatch function.


### -field NdkCreateListener

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439874">NDK_FN_CREATE_LISTENER</a> dispatch function.


### -field NdkBuildLAM

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439860">NDK_FN_BUILD_LAM</a> dispatch function.


### -field NdkReleaseLAM

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439910">NDK_FN_RELEASE_LAM</a> dispatch function.


## -remarks



The <b>NDK_ADAPTER_DISPATCH</b> structure is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439848">NDK_ADAPTER</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439848">NDK_ADAPTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439860">NDK_FN_BUILD_LAM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439872">NDK_FN_CREATE_CONNECTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439873">NDK_FN_CREATE_CQ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439874">NDK_FN_CREATE_LISTENER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439877">NDK_FN_CREATE_PD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439882">NDK_FN_CREATE_SHARED_ENDPOINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439904">NDK_FN_QUERY_ADAPTER_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439905">NDK_FN_QUERY_EXTENSION_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439910">NDK_FN_RELEASE_LAM</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_ADAPTER_DISPATCH structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
