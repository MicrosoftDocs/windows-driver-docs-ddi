---
UID: NS:ndkpi._NDK_QP
title: "_NDK_QP"
author: windows-driver-content
description: The NDK_QP structure specifies the attributes of an NDK queue pair (QP) object.
old-location: netvista\ndk_qp.htm
old-project: netvista
ms.assetid: 43491796-35CA-4E0C-90EF-7148651C68A6
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NDK_QP, NDK_QP structure [Network Drivers Starting with Windows Vista], _NDK_QP, ndkpi/NDK_QP, netvista.ndk_qp
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
-	NDK_QP
product: Windows
targetos: Windows
req.typenames: NDK_QP
---

# _NDK_QP structure


## -description


The <b>NDK_QP</b> structure specifies the attributes of an NDK queue pair (QP) object.


## -struct-fields




### -field Header

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439928">NDK_OBJECT_HEADER</a> structure for the <b>NDK_QP</b> structure. Set the <b>ObjectType</b> member of the structure that <b>Header</b> specifies to <b>NdkObjectTypeQp</b>.


### -field Dispatch

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh439934">NDK_QP_DISPATCH</a> structure that defines dispatch functions for the NDK QP object.


## -remarks



An NDK provider must set the <b>Dispatch</b> member to point to its  <a href="https://msdn.microsoft.com/library/windows/hardware/hh439934">NDK_QP_DISPATCH</a> table before returning the  created QP object. Also, the NDK provider must not use the <b>Dispatch</b> member after setting it because the NDK consumer can change the <b>Dispatch</b> member to some other value.




## -see-also




<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>



<a href="https://msdn.microsoft.com/2BF6F253-FCB4-4A61-9A67-81092F3C44E4">NDKPI Work Request Posting Requirements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439863">NDK_FN_CLOSE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439871">NDK_FN_CREATE_COMPLETION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439878">NDK_FN_CREATE_QP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439880">NDK_FN_CREATE_QP_WITH_SRQ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439928">NDK_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439934">NDK_QP_DISPATCH</a>
 

 

