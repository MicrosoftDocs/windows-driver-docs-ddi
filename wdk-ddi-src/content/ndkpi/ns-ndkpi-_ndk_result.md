---
UID: NS:ndkpi._NDK_RESULT
title: _NDK_RESULT (ndkpi.h)
description: The NDK_RESULT structure returns the results for an NDK request operation.
old-location: netvista\ndk_result.htm
tech.root: netvista
ms.assetid: B7898C81-E90D-4210-BEAE-1E629FCD7195
ms.date: 05/02/2018
keywords: ["_NDK_RESULT structure"]
ms.keywords: NDK_RESULT, NDK_RESULT structure [Network Drivers Starting with Windows Vista], _NDK_RESULT, ndkpi/NDK_RESULT, netvista.ndk_result
f1_keywords:
 - "ndkpi/NDK_RESULT"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndkpi.h
api_name:
- NDK_RESULT
product:
- Windows
targetos: Windows
req.typenames: NDK_RESULT
---

# _NDK_RESULT structure


## -description


The <b>NDK_RESULT</b> structure returns the results for an NDK request operation. 


## -struct-fields




### -field Status

The NDK request completion status.


### -field BytesTransferred

The number of bytes transferred. The value of this member  is valid only for <i>NdkReceive</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_receive">NDK_FN_RECEIVE</a>) request completions. The member is undefined for all other NDK request completions.


### -field QPContext

A context value for all requests that are posted over a queue pair (QP). The NDK consumer specified this  pointer when it called the <i>NdkCreateQp</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_qp">NDK_FN_CREATE_QP</a>) function to create the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_qp">NDK_QP</a> object.


### -field RequestContext

A request context value specified by the NDK consumer when  a request is posted.


## -remarks



 The <i>NdkGetCqResults</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_cq_results">NDK_FN_GET_CQ_RESULTS</a>)  function gets an array of <b>NDK_RESULT</b> structures that are filled with completion results that were removed from the CQ.






## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_qp">NDK_FN_CREATE_QP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_get_cq_results">NDK_FN_GET_CQ_RESULTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_receive">NDK_FN_RECEIVE</a>
 

 

