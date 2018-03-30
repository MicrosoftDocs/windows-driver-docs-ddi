---
UID: NC:ndkpi.NDK_FN_FLUSH
title: NDK_FN_FLUSH
author: windows-driver-content
description: The NdkFlush (NDK_FN_FLUSH) function initiates cancelling of the receive and the initiator queue requests that are currently pending on an NDK queue pair (QP) object.
old-location: netvista\ndk_fn_flush.htm
old-project: netvista
ms.assetid: 8C5F62DD-36CB-4EBC-9113-BB5BF19C0D45
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NDK_FN_FLUSH, NdkFlush, NdkFlush callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkFlush, netvista.ndk_fn_flush
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	NdkFlush
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_FLUSH callback


## -description


The <i>NdkFlush</i> (<i>NDK_FN_FLUSH</i>) function initiates cancelling of the receive and the initiator queue requests that are currently pending on an NDK queue pair (QP) object.


## -parameters




### -param *pNdkQp [in]

A pointer to an NDK queue pair (QP) object (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439933">NDK_QP</a>).


## -returns



None




## -remarks



<i>NdkFlush</i> cancels the receive and the initiator queue requests that are currently pending on a QP. The flushed requests have STATUS_CANCELLED as completion status.

If the  NDK consumer wants to verify that all of the requests are flushed after issuing <i>NdkFlush</i>, the consumer must empty the CQ until it sees completions for all requests that were queued prior to calling <i>NdkFlush</i>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439933">NDK_QP</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_FLUSH callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
