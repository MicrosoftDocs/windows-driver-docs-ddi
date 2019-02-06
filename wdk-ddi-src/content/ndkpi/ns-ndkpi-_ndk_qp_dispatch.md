---
UID: NS:ndkpi._NDK_QP_DISPATCH
title: _NDK_QP_DISPATCH (ndkpi.h)
description: The NDK_QP_DISPATCH structure specifies dispatch function entry points for the NDK queue pair (QP) object.
old-location: netvista\ndk_qp_dispatch.htm
tech.root: netvista
ms.assetid: C2B50C94-693A-48A2-8458-5722F652C933
ms.date: 05/02/2018
ms.keywords: NDK_QP_DISPATCH, NDK_QP_DISPATCH structure [Network Drivers Starting with Windows Vista], _NDK_QP_DISPATCH, ndkpi/NDK_QP_DISPATCH, netvista.ndk_qp_dispatch
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
-	NDK_QP_DISPATCH
product:
- Windows
targetos: Windows
req.typenames: NDK_QP_DISPATCH
---

# _NDK_QP_DISPATCH structure


## -description


The <b>NDK_QP_DISPATCH</b> structure specifies dispatch function entry points for the NDK queue pair (QP) object.


## -struct-fields




### -field NdkCloseQp

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439863">NDK_FN_CLOSE_OBJECT</a> dispatch function.


### -field NdkQueryExtension

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439905">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.


### -field NdkFlush

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439889">NDK_FN_FLUSH</a> dispatch function.


### -field NdkSend

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439914">NDK_FN_SEND</a> dispatch function.


### -field NdkReceive

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439907">NDK_FN_RECEIVE</a> dispatch function.


### -field NdkBind

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439859">NDK_FN_BIND</a> dispatch function.


### -field NdkFastRegister

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439887">NDK_FN_FAST_REGISTER</a> dispatch function.


### -field NdkInvalidate

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439901">NDK_FN_INVALIDATE</a> dispatch function.


### -field NdkRead

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439906">NDK_FN_READ</a> dispatch function.


### -field NdkWrite

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439917">NDK_FN_WRITE</a> dispatch function.


### -field NdkSendAndInvalidate

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/dn265507">NDK_FN_SEND_AND_INVALIDATE</a> dispatch function.

<b>Note</b>  This member is supported only in NDKPI 1.2 (Windows Server 2012 R2) and later.


## -remarks



The <b>NDK_QP_DISPATCH</b> structure is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439933">NDK_QP</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439859">NDK_FN_BIND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439863">NDK_FN_CLOSE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439887">NDK_FN_FAST_REGISTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439889">NDK_FN_FLUSH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439901">NDK_FN_INVALIDATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439905">NDK_FN_QUERY_EXTENSION_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439906">NDK_FN_READ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439907">NDK_FN_RECEIVE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439914">NDK_FN_SEND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439917">NDK_FN_WRITE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439933">NDK_QP</a>
 

 

