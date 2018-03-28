---
UID: NE:ndkpi._NDK_OBJECT_TYPE
title: "_NDK_OBJECT_TYPE"
author: windows-driver-content
description: The NDK_OBJECT_TYPE enumeration defines types of Network Direct Kernel (NDK) objects.
old-location: netvista\ndk_object_type.htm
old-project: netvista
ms.assetid: 8CB39DF6-00DA-4480-A44E-62CAF1DB35CE
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDK_OBJECT_TYPE, NDK_OBJECT_TYPE enumeration [Network Drivers Starting with Windows Vista], NdkObjectTypeAdapter, NdkObjectTypeConnector, NdkObjectTypeCq, NdkObjectTypeListener, NdkObjectTypeMax, NdkObjectTypeMr, NdkObjectTypeMw, NdkObjectTypePd, NdkObjectTypeQp, NdkObjectTypeSharedEndpoint, NdkObjectTypeSrq, NdkObjectTypeUndefined, _NDK_OBJECT_TYPE, ndkpi/NDK_OBJECT_TYPE, ndkpi/NdkObjectTypeAdapter, ndkpi/NdkObjectTypeConnector, ndkpi/NdkObjectTypeCq, ndkpi/NdkObjectTypeListener, ndkpi/NdkObjectTypeMax, ndkpi/NdkObjectTypeMr, ndkpi/NdkObjectTypeMw, ndkpi/NdkObjectTypePd, ndkpi/NdkObjectTypeQp, ndkpi/NdkObjectTypeSharedEndpoint, ndkpi/NdkObjectTypeSrq, ndkpi/NdkObjectTypeUndefined, netvista.ndk_object_type
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndkpi.h
api_name:
-	NDK_OBJECT_TYPE
product: Windows
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

Specifies an NDK adapter object (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439848">NDK_ADAPTER</a>).


### -field NdkObjectTypeQp

Specifies an NDK queue pair (QP) object (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439933">NDK_QP</a>).


### -field NdkObjectTypeCq

Specifies an NDK completion queue (CQ) object (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439854">NDK_CQ</a>).


### -field NdkObjectTypeMr

Specifies an NDK memory region (MR) object (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439922">NDK_MR</a>).


### -field NdkObjectTypeMw

Specifies an NDK memory window (MW) object (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439926">NDK_MW</a>).


### -field NdkObjectTypePd

Specifies an NDK protection domain (PD) object (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439931">NDK_PD</a>).


### -field NdkObjectTypeSharedEndpoint

Specifies an NDK shared endpoint object (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439937">NDK_SHARED_ENDPOINT</a>).


### -field NdkObjectTypeConnector

Specifies an NDK connector object (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439852">NDK_CONNECTOR</a>).


### -field NdkObjectTypeListener

Specifies an NDK listener object (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439918">NDK_LISTENER</a>).


### -field NdkObjectTypeSrq

Specifies an NDK shared receive queue (SRQ) object (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439939">NDK_SRQ</a>).


### -field NdkObjectTypeMax

The maximum value for this enumeration. This value might change in future versions of the header files and binaries. 




## -remarks



NDK objects include an <a href="https://msdn.microsoft.com/library/windows/hardware/hh439928">NDK_OBJECT_HEADER</a> structure that packages the object type,  version, and other information.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439848">NDK_ADAPTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439852">NDK_CONNECTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439854">NDK_CQ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439918">NDK_LISTENER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439922">NDK_MR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439926">NDK_MW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439928">NDK_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439931">NDK_PD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439933">NDK_QP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439937">NDK_SHARED_ENDPOINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439939">NDK_SRQ</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_OBJECT_TYPE enumeration%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

