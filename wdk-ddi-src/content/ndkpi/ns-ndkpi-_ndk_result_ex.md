---
UID: NS:ndkpi._NDK_RESULT_EX
title: _NDK_RESULT_EX (ndkpi.h)
description: The NDK_RESULT_EX structure returns the results for an NDK request operation. It is identical to the NDK_RESULT structure, except that it has additional Type and TypeSpecificCompletionOutput members.
old-location: netvista\ndk_result_ex.htm
tech.root: netvista
ms.assetid: C79BF9FC-4836-48AD-8E9F-41278BB01E11
ms.date: 05/02/2018
keywords: ["NDK_RESULT_EX structure"]
ms.keywords: NDK_RESULT_EX, NDK_RESULT_EX structure [Network Drivers Starting with Windows Vista], PNDK_RESULT_EX, PNDK_RESULT_EX structure pointer [Network Drivers Starting with Windows Vista], _NDK_RESULT_EX, ndkpi/NDK_RESULT_EX, ndkpi/PNDK_RESULT_EX, netvista.ndk_result_ex
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
req.irql: 
targetos: Windows
req.typenames: NDK_RESULT_EX
f1_keywords:
 - _NDK_RESULT_EX
 - ndkpi/_NDK_RESULT_EX
 - NDK_RESULT_EX
 - ndkpi/NDK_RESULT_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndkpi.h
api_name:
 - NDK_RESULT_EX
---

# _NDK_RESULT_EX structure


## -description

The <b>NDK_RESULT_EX</b> structure returns the results for an NDK request operation. It is identical to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_result">NDK_RESULT</a> structure, except that it has additional <b>Type</b> and <b>TypeSpecificCompletionOutput</b> members.

## -struct-fields

### -field Status

The NDK request completion status.

### -field BytesTransferred

The number of bytes transferred. The value of this member  is valid only for <i>NdkReceive</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_receive">NDK_FN_RECEIVE</a>) request completions. The member is undefined for all other NDK request completions.

### -field QPContext

A context value for all requests that are posted over a queue pair (QP). The NDK consumer specified this  pointer when it called the <i>NdkCreateQp</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_qp">NDK_FN_CREATE_QP</a>) function to create the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_qp">NDK_QP</a> object.

### -field RequestContext

A request context value specified by the NDK consumer when  a request is posted.

### -field Type

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ne-ndkpi-_ndk_operation_type">NDK_OPERATION_TYPE</a> enumeration value that specifies the type of operation that is being completed.

### -field TypeSpecificCompletionOutput

The type-specific completion output, if any. If the  <b>Type</b> member is <b>NdkOperationTypeReceiveAndInvalidate</b>, this member is a 32-bit field, which contains the token to be invalidated before signaling this completion. Otherwise, this member is undefined.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_qp">NDK_FN_CREATE_QP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ne-ndkpi-_ndk_operation_type">NDK_OPERATION_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_qp">NDK_QP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_result">NDK_RESULT</a>

