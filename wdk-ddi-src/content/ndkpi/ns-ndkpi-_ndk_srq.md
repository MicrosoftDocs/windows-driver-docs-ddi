---
UID: NS:ndkpi._NDK_SRQ
title: "_NDK_SRQ"
author: windows-driver-content
description: The NDK_SRQ structure specifies the attributes of an NDK shared receive queue (SRQ) object.
old-location: netvista\ndk_srq.htm
old-project: netvista
ms.assetid: BDD2E8A6-D233-4581-AC1D-B6E33919898E
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NDK_SRQ, NDK_SRQ structure [Network Drivers Starting with Windows Vista], PNDK_SRQ, PNDK_SRQ structure pointer [Network Drivers Starting with Windows Vista], _NDK_SRQ, ndkpi/NDK_SRQ, ndkpi/PNDK_SRQ, netvista.ndk_srq
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndkpi.h
api_name:
-	NDK_SRQ
product: Windows
targetos: Windows
req.typenames: NDK_SRQ
---

# _NDK_SRQ structure


## -description


The <b>NDK_SRQ</b> structure specifies the attributes of an NDK shared receive queue (SRQ) object.


## -struct-fields




### -field Header

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439928">NDK_OBJECT_HEADER</a> structure for the NDK_SRQ structure. Set the <b>ObjectType</b> member of the structure that <b>Header</b> specifies to <b>NdkObjectTypeSrq</b>.


### -field Dispatch

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh439940">NDK_SRQ_DISPATCH</a> structure that defines dispatch functions for the NDK SRQ object.


## -remarks



An NDK provider must set the <b>Dispatch</b> member to point to its  <a href="https://msdn.microsoft.com/library/windows/hardware/hh439940">NDK_SRQ_DISPATCH</a> table before returning the  created SRQ object. Also, the NDK provider must not use the <b>Dispatch</b> member after setting it because the NDK consumer can change the <b>Dispatch</b> member to some other value.




## -see-also




<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>



<a href="https://msdn.microsoft.com/2BF6F253-FCB4-4A61-9A67-81092F3C44E4">NDKPI Work Request Posting Requirements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439863">NDK_FN_CLOSE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439871">NDK_FN_CREATE_COMPLETION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439880">NDK_FN_CREATE_QP_WITH_SRQ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439883">NDK_FN_CREATE_SRQ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439928">NDK_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439940">NDK_SRQ_DISPATCH</a>
 

 

