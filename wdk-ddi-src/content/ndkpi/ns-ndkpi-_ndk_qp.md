---
UID: NS:ndkpi._NDK_QP
title: _NDK_QP (ndkpi.h)
description: The NDK_QP structure specifies the attributes of an NDK queue pair (QP) object.
old-location: netvista\ndk_qp.htm
tech.root: netvista
ms.assetid: 43491796-35CA-4E0C-90EF-7148651C68A6
ms.date: 05/02/2018
ms.keywords: NDK_QP, NDK_QP structure [Network Drivers Starting with Windows Vista], _NDK_QP, ndkpi/NDK_QP, netvista.ndk_qp
ms.topic: struct
f1_keywords:
 - "ndkpi/NDK_QP"
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
- NDK_QP
product:
- Windows
targetos: Windows
req.typenames: NDK_QP
---

# _NDK_QP structure


## -description


The <b>NDK_QP</b> structure specifies the attributes of an NDK queue pair (QP) object.


## -struct-fields




### -field Header

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_object_header">NDK_OBJECT_HEADER</a> structure for the <b>NDK_QP</b> structure. Set the <b>ObjectType</b> member of the structure that <b>Header</b> specifies to <b>NdkObjectTypeQp</b>.


### -field Dispatch

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_qp_dispatch">NDK_QP_DISPATCH</a> structure that defines dispatch functions for the NDK QP object.


## -remarks



An NDK provider must set the <b>Dispatch</b> member to point to its  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_qp_dispatch">NDK_QP_DISPATCH</a> table before returning the  created QP object. Also, the NDK provider must not use the <b>Dispatch</b> member after setting it because the NDK consumer can change the <b>Dispatch</b> member to some other value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndkpi-object-lifetime-requirements">NDKPI Object Lifetime Requirements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndkpi-work-request-posting-requirements">NDKPI Work Request Posting Requirements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_close_object">NDK_FN_CLOSE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_qp">NDK_FN_CREATE_QP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_qp_with_srq">NDK_FN_CREATE_QP_WITH_SRQ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_object_header">NDK_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_qp_dispatch">NDK_QP_DISPATCH</a>
 

 

