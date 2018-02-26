---
UID: NS:ndkpi._NDK_RESULT_EX
title: "_NDK_RESULT_EX"
author: windows-driver-content
description: The NDK_RESULT_EX structure returns the results for an NDK request operation. It is identical to the NDK_RESULT structure, except that it has additional Type and TypeSpecificCompletionOutput members.
old-location: netvista\ndk_result_ex.htm
old-project: netvista
ms.assetid: C79BF9FC-4836-48AD-8E9F-41278BB01E11
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , ,, D, E, K, L, N, NDK_RESULT_EX, NDK_RESULT_EX structure [Network Drivers Starting with Windows Vista], PNDK_RESULT_EX, PNDK_RESULT_EX structure pointer [Network Drivers Starting with Windows Vista], R, S, T, U, X, _, _NDK_RESULT_EX, ndkpi/NDK_RESULT_EX, ndkpi/PNDK_RESULT_EX, netvista.ndk_result_ex"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.40 and later.
req.target-min-winversvr: Windows Server 2012 R2
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndkpi.h
apiname:
-	NDK_RESULT_EX
product: Windows
targetos: Windows
req.typenames: NDK_RESULT_EX
---

# _NDK_RESULT_EX structure


## -description


The <b>NDK_RESULT_EX</b> structure returns the results for an NDK request operation. It is identical to the <a href="..\ndkpi\ns-ndkpi-_ndk_result.md">NDK_RESULT</a> structure, except that it has additional <b>Type</b> and <b>TypeSpecificCompletionOutput</b> members.


## -syntax


````
typedef struct _NDK_RESULT_EX {
  NTSTATUS           Status;
  ULONG              BytesTransferred;
  PVOID              QPContext;
  PVOID              RequestContext;
  NDK_OPERATION_TYPE Type;
  ULONG_PTR          TypeSpecificCompletionOutput;
} NDK_RESULT_EX, *PNDK_RESULT_EX;
````


## -struct-fields




### -field Status

The NDK request completion status.


### -field BytesTransferred

The number of bytes transferred. The value of this member  is valid only for <i>NdkReceive</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_receive.md">NDK_FN_RECEIVE</a>) request completions. The member is undefined for all other NDK request completions.


### -field QPContext

A context value for all requests that are posted over a queue pair (QP). The NDK consumer specified this  pointer when it called the <i>NdkCreateQp</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_qp.md">NDK_FN_CREATE_QP</a>) function to create the <a href="..\ndkpi\ns-ndkpi-_ndk_qp.md">NDK_QP</a> object.


### -field RequestContext

A request context value specified by the NDK consumer when  a request is posted.


### -field Type

An <a href="..\ndkpi\ne-ndkpi-_ndk_operation_type.md">NDK_OPERATION_TYPE</a> enumeration value that specifies the type of operation that is being completed.


### -field TypeSpecificCompletionOutput

The type-specific completion output, if any. If the  <b>Type</b> member is <b>NdkOperationTypeReceiveAndInvalidate</b>, this member is a 32-bit field, which contains the token to be invalidated before signaling this completion. Otherwise, this member is undefined.


## -see-also

<a href="..\ndkpi\ns-ndkpi-_ndk_result.md">NDK_RESULT</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_qp.md">NDK_QP</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_qp.md">NDK_FN_CREATE_QP</a>



<a href="..\ndkpi\ne-ndkpi-_ndk_operation_type.md">NDK_OPERATION_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_RESULT_EX structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

