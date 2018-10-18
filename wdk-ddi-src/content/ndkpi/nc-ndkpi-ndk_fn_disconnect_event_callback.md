---
UID: NC:ndkpi.NDK_FN_DISCONNECT_EVENT_CALLBACK
title: NDK_FN_DISCONNECT_EVENT_CALLBACK
author: windows-driver-content
description: The NdkDisconnectEventCallback (NDK_FN_DISCONNECT_EVENT_CALLBACK) function is called by the NDK provider once when the peer disconnects.
old-location: netvista\ndk_fn_disconnect_event_callback.htm
tech.root: netvista
ms.assetid: AC6A7CD4-D553-4E6D-B6BF-C30CDA541EB5
ms.date: 05/02/2018
ms.keywords: NDK_FN_DISCONNECT_EVENT_CALLBACK, NDK_FN_DISCONNECT_EVENT_CALLBACK callback, NdkDisconnectEventCallback, NdkDisconnectEventCallback callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkDisconnectEventCallback, netvista.ndk_fn_disconnect_event_callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ndkpi.h
api_name:
-	NdkDisconnectEventCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDK_FN_DISCONNECT_EVENT_CALLBACK callback function


## -description


The <i>NdkDisconnectEventCallback</i> (<i>NDK_FN_DISCONNECT_EVENT_CALLBACK</i>) function  is called by the NDK provider once when the peer disconnects. 


## -parameters




### -param DisconnectEventContext [in, optional]

A context area that was specified in the <i>DisconnectEvent</i> parameter of the <i>NdkCompleteConnect</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439864">NDK_FN_COMPLETE_CONNECT</a>)  or <i>NdkAccept</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439857">NDK_FN_ACCEPT</a>)  function when the completion queue (CQ)  object was created.


## -returns



None




## -remarks



<div class="alert"><b>Note</b>  This routine is implemented by the NDK consumer and passed to the NDK provider.</div>
<div> </div>
<i>NdkDisconnectEventCallback</i> is a callback function for connection disconnect events.  A disconnect notification callback function is specified for a connection with the <i>NdkCompleteConnect</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439864">NDK_FN_COMPLETE_CONNECT</a>) function on the initiator side and with the <i>NdkAccept</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439857">NDK_FN_ACCEPT</a>) function on the listener side. The NDK provider invokes this callback only once when the peer disconnects. The provider should not flush outstanding work requests when it indicates a disconnect event because of an incoming disconnect request from the peer.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439857">NDK_FN_ACCEPT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439864">NDK_FN_COMPLETE_CONNECT</a>
 

 

