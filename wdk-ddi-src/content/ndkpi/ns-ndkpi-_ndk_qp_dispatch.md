---
UID: NS:ndkpi._NDK_QP_DISPATCH
title: "_NDK_QP_DISPATCH"
author: windows-driver-content
description: The NDK_QP_DISPATCH structure specifies dispatch function entry points for the NDK queue pair (QP) object.
old-location: netvista\ndk_qp_dispatch.htm
old-project: netvista
ms.assetid: C2B50C94-693A-48A2-8458-5722F652C933
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: NDK_QP_DISPATCH, NDK_QP_DISPATCH structure [Network Drivers Starting with Windows Vista], _NDK_QP_DISPATCH, ndkpi/NDK_QP_DISPATCH, netvista.ndk_qp_dispatch
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
-	NDK_QP_DISPATCH
product: Windows
targetos: Windows
req.typenames: NDK_QP_DISPATCH
---

# _NDK_QP_DISPATCH structure


## -description


The <b>NDK_QP_DISPATCH</b> structure specifies dispatch function entry points for the NDK queue pair (QP) object.


## -syntax


````
typedef struct _NDK_QP_DISPATCH {
  NDK_FN_CLOSE_OBJECT              NdkCloseQp;
  NDK_FN_QUERY_EXTENSION_INTERFACE NdkQueryExtension;
  NDK_FN_FLUSH                     NdkFlush;
  NDK_FN_SEND                      NdkSend;
  NDK_FN_RECEIVE                   NdkReceive;
  NDK_FN_BIND                      NdkBind;
  NDK_FN_FAST_REGISTER             NdkFastRegister;
  NDK_FN_INVALIDATE                NdkInvalidate;
  NDK_FN_READ                      NdkRead;
  NDK_FN_WRITE                     NdkWrite;
  NDK_FN_SEND_AND_INVALIDATE       NdkSendAndInvalidate;
} NDK_QP_DISPATCH;
````


## -struct-fields




### -field NdkCloseQp

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a> dispatch function.


### -field NdkQueryExtension

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_query_extension_interface.md">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.


### -field NdkFlush

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_flush.md">NDK_FN_FLUSH</a> dispatch function.


### -field NdkSend

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_send.md">NDK_FN_SEND</a> dispatch function.


### -field NdkReceive

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_receive.md">NDK_FN_RECEIVE</a> dispatch function.


### -field NdkBind

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_bind.md">NDK_FN_BIND</a> dispatch function.


### -field NdkFastRegister

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_fast_register.md">NDK_FN_FAST_REGISTER</a> dispatch function.


### -field NdkInvalidate

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_invalidate.md">NDK_FN_INVALIDATE</a> dispatch function.


### -field NdkRead

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_read.md">NDK_FN_READ</a> dispatch function.


### -field NdkWrite

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_write.md">NDK_FN_WRITE</a> dispatch function.


### -field NdkSendAndInvalidate

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_send_and_invalidate.md">NDK_FN_SEND_AND_INVALIDATE</a> dispatch function.

<b>Note</b>  This member is supported only in NDKPI 1.2 (Windows Server 2012 R2) and later.


## -remarks



The <b>NDK_QP_DISPATCH</b> structure is used in the <a href="..\ndkpi\ns-ndkpi-_ndk_qp.md">NDK_QP</a> structure.




## -see-also

<a href="..\ndkpi\nc-ndkpi-ndk_fn_invalidate.md">NDK_FN_INVALIDATE</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_read.md">NDK_FN_READ</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_write.md">NDK_FN_WRITE</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_qp.md">NDK_QP</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_send.md">NDK_FN_SEND</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_bind.md">NDK_FN_BIND</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_receive.md">NDK_FN_RECEIVE</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_fast_register.md">NDK_FN_FAST_REGISTER</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_flush.md">NDK_FN_FLUSH</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_query_extension_interface.md">NDK_FN_QUERY_EXTENSION_INTERFACE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_QP_DISPATCH structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

