---
UID: NE:ndkpi._NDK_OBJECT_TYPE
title: _NDK_OBJECT_TYPE (ndkpi.h)
description: The NDK_OBJECT_TYPE enumeration defines types of Network Direct Kernel (NDK) objects.
old-location: netvista\ndk_object_type.htm
tech.root: netvista
ms.assetid: 8CB39DF6-00DA-4480-A44E-62CAF1DB35CE
ms.date: 05/02/2018
ms.keywords: NDK_OBJECT_TYPE, NDK_OBJECT_TYPE enumeration [Network Drivers Starting with Windows Vista], NdkObjectTypeAdapter, NdkObjectTypeConnector, NdkObjectTypeCq, NdkObjectTypeListener, NdkObjectTypeMax, NdkObjectTypeMr, NdkObjectTypeMw, NdkObjectTypePd, NdkObjectTypeQp, NdkObjectTypeSharedEndpoint, NdkObjectTypeSrq, NdkObjectTypeUndefined, _NDK_OBJECT_TYPE, ndkpi/NDK_OBJECT_TYPE, ndkpi/NdkObjectTypeAdapter, ndkpi/NdkObjectTypeConnector, ndkpi/NdkObjectTypeCq, ndkpi/NdkObjectTypeListener, ndkpi/NdkObjectTypeMax, ndkpi/NdkObjectTypeMr, ndkpi/NdkObjectTypeMw, ndkpi/NdkObjectTypePd, ndkpi/NdkObjectTypeQp, ndkpi/NdkObjectTypeSharedEndpoint, ndkpi/NdkObjectTypeSrq, ndkpi/NdkObjectTypeUndefined, netvista.ndk_object_type
ms.topic: enum
f1_keywords:
 - "ndkpi/NDK_OBJECT_TYPE"
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
- NDK_OBJECT_TYPE
product:
- Windows
targetos: Windows
req.typenames: NDK_OBJECT_TYPE
---

# _NDK_OBJECT_TYPE enumeration


## -description


The <b>NDK_OBJECT_TYPE</b> enumeration defines  types of Network Direct Kernel (NDK) objects.


## -enum-fields




### -field NdkObjectTypeUndefined

Specifies  an undefined NDK  object.


### -field NdkObjectTypeAdapter

Specifies an NDK adapter object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_adapter">NDK_ADAPTER</a>).


### -field NdkObjectTypeQp

Specifies an NDK queue pair (QP) object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_qp">NDK_QP</a>).


### -field NdkObjectTypeCq

Specifies an NDK completion queue (CQ) object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_cq">NDK_CQ</a>).


### -field NdkObjectTypeMr

Specifies an NDK memory region (MR) object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_mr">NDK_MR</a>).


### -field NdkObjectTypeMw

Specifies an NDK memory window (MW) object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_mw">NDK_MW</a>).


### -field NdkObjectTypePd

Specifies an NDK protection domain (PD) object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_pd">NDK_PD</a>).


### -field NdkObjectTypeSharedEndpoint

Specifies an NDK shared endpoint object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_shared_endpoint">NDK_SHARED_ENDPOINT</a>).


### -field NdkObjectTypeConnector

Specifies an NDK connector object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector">NDK_CONNECTOR</a>).


### -field NdkObjectTypeListener

Specifies an NDK listener object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_listener">NDK_LISTENER</a>).


### -field NdkObjectTypeSrq

Specifies an NDK shared receive queue (SRQ) object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_srq">NDK_SRQ</a>).


### -field NdkObjectTypeMax

The maximum value for this enumeration. This value might change in future versions of the header files and binaries. 




## -remarks



NDK objects include an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_object_header">NDK_OBJECT_HEADER</a> structure that packages the object type,  version, and other information.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_adapter">NDK_ADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_connector">NDK_CONNECTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_cq">NDK_CQ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_listener">NDK_LISTENER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_mr">NDK_MR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_mw">NDK_MW</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_object_header">NDK_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_pd">NDK_PD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_qp">NDK_QP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_shared_endpoint">NDK_SHARED_ENDPOINT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_srq">NDK_SRQ</a>
 

 

