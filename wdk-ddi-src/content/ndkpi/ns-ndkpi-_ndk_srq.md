---
UID: NS:ndkpi._NDK_SRQ
title: _NDK_SRQ (ndkpi.h)
description: The NDK_SRQ structure specifies the attributes of an NDK shared receive queue (SRQ) object.
old-location: netvista\ndk_srq.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDK_SRQ structure"]
ms.keywords: NDK_SRQ, NDK_SRQ structure [Network Drivers Starting with Windows Vista], PNDK_SRQ, PNDK_SRQ structure pointer [Network Drivers Starting with Windows Vista], _NDK_SRQ, ndkpi/NDK_SRQ, ndkpi/PNDK_SRQ, netvista.ndk_srq
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
targetos: Windows
req.typenames: NDK_SRQ
f1_keywords:
 - _NDK_SRQ
 - ndkpi/_NDK_SRQ
 - NDK_SRQ
 - ndkpi/NDK_SRQ
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndkpi.h
api_name:
 - _NDK_SRQ
 - NDK_SRQ
---

# _NDK_SRQ structure


## -description

The <b>NDK_SRQ</b> structure specifies the attributes of an NDK shared receive queue (SRQ) object.

## -struct-fields

### -field Header

The <a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_object_header">NDK_OBJECT_HEADER</a> structure for the NDK_SRQ structure. Set the <b>ObjectType</b> member of the structure that <b>Header</b> specifies to <b>NdkObjectTypeSrq</b>.

### -field Dispatch

A pointer to an <a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_srq_dispatch">NDK_SRQ_DISPATCH</a> structure that defines dispatch functions for the NDK SRQ object.

## -remarks

An NDK provider must set the <b>Dispatch</b> member to point to its  <a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_srq_dispatch">NDK_SRQ_DISPATCH</a> table before returning the  created SRQ object. Also, the NDK provider must not use the <b>Dispatch</b> member after setting it because the NDK consumer can change the <b>Dispatch</b> member to some other value.

## -see-also

<a href="/windows-hardware/drivers/network/ndkpi-object-lifetime-requirements">NDKPI Object Lifetime Requirements</a>



<a href="/windows-hardware/drivers/network/ndkpi-work-request-posting-requirements">NDKPI Work Request Posting Requirements</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_close_object">NDK_FN_CLOSE_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_qp_with_srq">NDK_FN_CREATE_QP_WITH_SRQ</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_srq">NDK_FN_CREATE_SRQ</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_object_header">NDK_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_srq_dispatch">NDK_SRQ_DISPATCH</a>

