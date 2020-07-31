---
UID: NS:ndkpi._NDK_CQ
title: _NDK_CQ (ndkpi.h)
description: The NDK_CQ structure specifies the attributes of an NDK completion queue (CQ) object.
old-location: netvista\ndk_cq.htm
tech.root: netvista
ms.assetid: FE5E1E5F-3EEC-4FF4-B275-E2B086ADCDCC
ms.date: 05/02/2018
keywords: ["_NDK_CQ structure"]
ms.keywords: NDK_CQ, NDK_CQ structure [Network Drivers Starting with Windows Vista], PNDK_CQ, PNDK_CQ structure pointer [Network Drivers Starting with Windows Vista], _NDK_CQ, ndkpi/NDK_CQ, ndkpi/PNDK_CQ, netvista.ndk_cq
f1_keywords:
 - "ndkpi/NDK_CQ"
 - "NDK_CQ"
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
- NDK_CQ
targetos: Windows
req.typenames: NDK_CQ
---

# _NDK_CQ structure


## -description


The <b>NDK_CQ</b> structure specifies the attributes of an NDK completion queue (CQ) object.


## -struct-fields




### -field Header

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_object_header">NDK_OBJECT_HEADER</a> structure for the NDK_CQ structure. Set the <b>ObjectType</b> member of the structure that <b>Header</b> specifies to <b>NdkObjectTypeCq</b>.


### -field Dispatch

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_cq_dispatch">NDK_CQ_DISPATCH</a> structure that defines dispatch functions for the NDK CQ object.


## -remarks



An NDK provider must set the <b>Dispatch</b> member to point to its  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_cq_dispatch">NDK_CQ_DISPATCH</a> table before returning the  created CQ object. Also, the NDK provider must not use the <b>Dispatch</b> member after setting it because the NDK consumer can change the <b>Dispatch</b> member to some other value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndkpi-completion-handling-requirements">NDKPI Completion Handling Requirements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndkpi-object-lifetime-requirements">NDKPI Object Lifetime Requirements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_cq_dispatch">NDK_CQ_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_close_object">NDK_FN_CLOSE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_create_cq">NDK_FN_CREATE_CQ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_object_header">NDK_OBJECT_HEADER</a>
 

 

