---
UID: NE:ndkpi._NDK_OBJECT_TYPE
title: "_NDK_OBJECT_TYPE"
author: windows-driver-content
description: The NDK_OBJECT_TYPE enumeration defines types of Network Direct Kernel (NDK) objects.
old-location: netvista\ndk_object_type.htm
old-project: netvista
ms.assetid: 8CB39DF6-00DA-4480-A44E-62CAF1DB35CE
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndkpi/NdkObjectTypeListener, _NDK_OBJECT_TYPE, ndkpi/NDK_OBJECT_TYPE, ndkpi/NdkObjectTypeSrq, ndkpi/NdkObjectTypeAdapter, NdkObjectTypeListener, netvista.ndk_object_type, ndkpi/NdkObjectTypeSharedEndpoint, ndkpi/NdkObjectTypeUndefined, NDK_OBJECT_TYPE, ndkpi/NdkObjectTypeCq, NdkObjectTypeMr, NDK_OBJECT_TYPE enumeration [Network Drivers Starting with Windows Vista], NdkObjectTypeQp, NdkObjectTypeCq, ndkpi/NdkObjectTypeQp, NdkObjectTypeSrq, NdkObjectTypeSharedEndpoint, ndkpi/NdkObjectTypeMw, NdkObjectTypeMw, NdkObjectTypeMax, ndkpi/NdkObjectTypeMax, ndkpi/NdkObjectTypePd, NdkObjectTypePd, NdkObjectTypeUndefined, NdkObjectTypeAdapter, ndkpi/NdkObjectTypeMr, ndkpi/NdkObjectTypeConnector, NdkObjectTypeConnector
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndkpi.h
apiname:
-	NDK_OBJECT_TYPE
product: Windows
targetos: Windows
req.typenames: NDK_OBJECT_TYPE
---

# _NDK_OBJECT_TYPE enumeration


## -description


The <b>NDK_OBJECT_TYPE</b> enumeration defines  types of Network Direct Kernel (NDK) objects.


## -syntax


````
typedef enum _NDK_OBJECT_TYPE { 
  NdkObjectTypeUndefined       = 0,
  NdkObjectTypeAdapter         = 1,
  NdkObjectTypeQp              = 2,
  NdkObjectTypeCq              = 3,
  NdkObjectTypeMr              = 4,
  NdkObjectTypeMw              = 5,
  NdkObjectTypePd              = 6,
  NdkObjectTypeSharedEndpoint  = 7,
  NdkObjectTypeConnector       = 8,
  NdkObjectTypeListener        = 9,
  NdkObjectTypeSrq             = 10,
  NdkObjectTypeMax             = 11
} NDK_OBJECT_TYPE;
````


## -enum-fields




#### - NdkObjectTypeUndefined

Specifies  an undefined NDK  object.


#### - NdkObjectTypeAdapter

Specifies an NDK adapter object (<a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER</a>).


#### - NdkObjectTypeQp

Specifies an NDK queue pair (QP) object (<a href="..\ndkpi\ns-ndkpi-_ndk_qp.md">NDK_QP</a>).


#### - NdkObjectTypeCq

Specifies an NDK completion queue (CQ) object (<a href="..\ndkpi\ns-ndkpi-_ndk_cq.md">NDK_CQ</a>).


#### - NdkObjectTypeMr

Specifies an NDK memory region (MR) object (<a href="..\ndkpi\ns-ndkpi-_ndk_mr.md">NDK_MR</a>).


#### - NdkObjectTypeMw

Specifies an NDK memory window (MW) object (<a href="..\ndkpi\ns-ndkpi-_ndk_mw.md">NDK_MW</a>).


#### - NdkObjectTypePd

Specifies an NDK protection domain (PD) object (<a href="..\ndkpi\ns-ndkpi-_ndk_pd.md">NDK_PD</a>).


#### - NdkObjectTypeSharedEndpoint

Specifies an NDK shared endpoint object (<a href="..\ndkpi\ns-ndkpi-_ndk_shared_endpoint.md">NDK_SHARED_ENDPOINT</a>).


#### - NdkObjectTypeConnector

Specifies an NDK connector object (<a href="..\ndkpi\ns-ndkpi-_ndk_connector.md">NDK_CONNECTOR</a>).


#### - NdkObjectTypeListener

Specifies an NDK listener object (<a href="..\ndkpi\ns-ndkpi-_ndk_listener.md">NDK_LISTENER</a>).


#### - NdkObjectTypeSrq

Specifies an NDK shared receive queue (SRQ) object (<a href="..\ndkpi\ns-ndkpi-_ndk_srq.md">NDK_SRQ</a>).


#### - NdkObjectTypeMax

The maximum value for this enumeration. This value might change in future versions of the header files and binaries. 




## -remarks


NDK objects include an <a href="..\ndkpi\ns-ndkpi-_ndk_object_header.md">NDK_OBJECT_HEADER</a> structure that packages the object type,  version, and other information.



## -see-also

<a href="..\ndkpi\ns-ndkpi-_ndk_object_header.md">NDK_OBJECT_HEADER</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_connector.md">NDK_CONNECTOR</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_cq.md">NDK_CQ</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_pd.md">NDK_PD</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_mw.md">NDK_MW</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_srq.md">NDK_SRQ</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_listener.md">NDK_LISTENER</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_shared_endpoint.md">NDK_SHARED_ENDPOINT</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_mr.md">NDK_MR</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_qp.md">NDK_QP</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_OBJECT_TYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

