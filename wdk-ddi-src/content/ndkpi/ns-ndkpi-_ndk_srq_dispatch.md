---
UID: NS:ndkpi._NDK_SRQ_DISPATCH
title: "_NDK_SRQ_DISPATCH"
author: windows-driver-content
description: The NDK_SRQ_DISPATCH structure specifies dispatch function entry points for the NDK shared receive queue (SRQ) object.
old-location: netvista\ndk_srq_dispatch.htm
old-project: netvista
ms.assetid: 13297898-A72B-4771-A022-FDCBC281CEA0
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NDK_SRQ_DISPATCH, NDK_SRQ_DISPATCH structure [Network Drivers Starting with Windows Vista], _NDK_SRQ_DISPATCH, ndkpi/NDK_SRQ_DISPATCH, netvista.ndk_srq_dispatch
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
-	NDK_SRQ_DISPATCH
product: Windows
targetos: Windows
req.typenames: NDK_SRQ_DISPATCH
---

# _NDK_SRQ_DISPATCH structure


## -description


The <b>NDK_SRQ_DISPATCH</b> structure specifies dispatch function entry points for the NDK shared receive queue (SRQ) object.


## -struct-fields




### -field NdkCloseSrq

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439863">NDK_FN_CLOSE_OBJECT</a> dispatch function.


### -field NdkQueryExtension

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439905">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.


### -field NdkModifySrq

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439903">NDK_FN_MODIFY_SRQ</a> dispatch function.


### -field NdkSrqReceive

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439916">NDK_FN_SRQ_RECEIVE</a> dispatch function.


## -remarks



The <b>NDK_SRQ_DISPATCH</b> structure is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439939">NDK_SRQ</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439863">NDK_FN_CLOSE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439903">NDK_FN_MODIFY_SRQ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439905">NDK_FN_QUERY_EXTENSION_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439916">NDK_FN_SRQ_RECEIVE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439939">NDK_SRQ</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_SRQ_DISPATCH structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
