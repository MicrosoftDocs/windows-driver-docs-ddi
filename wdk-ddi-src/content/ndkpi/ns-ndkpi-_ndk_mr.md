---
UID: NS:ndkpi._NDK_MR
title: "_NDK_MR"
author: windows-driver-content
description: The NDK_MR structure specifies the attributes of an NDK memory region (MR) object.
old-location: netvista\ndk_mr.htm
old-project: netvista
ms.assetid: F0585210-048E-4397-98E4-46640731E66C
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NDK_MR, NDK_MR structure [Network Drivers Starting with Windows Vista], PNDK_MR, PNDK_MR structure pointer [Network Drivers Starting with Windows Vista], _NDK_MR, ndkpi/NDK_MR, ndkpi/PNDK_MR, netvista.ndk_mr
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndkpi.h
api_name:
-	NDK_MR
product: Windows
targetos: Windows
req.typenames: NDK_MR, NDK_MR
---

# _NDK_MR structure


## -description


The <b>NDK_MR</b> structure specifies the attributes of an NDK memory region (MR) object.


## -syntax


````
typedef struct _NDK_MR {
  NDK_OBJECT_HEADER     Header;
  CONST NDK_MR_DISPATCH *Dispatch;
} NDK_MR, *PNDK_MR;
````


## -struct-fields




### -field Header

The <a href="..\ndkpi\ns-ndkpi-_ndk_object_header.md">NDK_OBJECT_HEADER</a> structure for the <b>NDK_MR</b> structure. Set the <b>ObjectType</b> member of the structure that <b>Header</b> specifies to <b>NdkObjectTypeMr</b>.


### -field Dispatch

A pointer to an <a href="..\ndkpi\ns-ndkpi-_ndk_mr_dispatch.md">NDK_MR_DISPATCH</a> structure that defines dispatch functions for the NDK MR object.


## -remarks



An NDK provider must set the <b>Dispatch</b> member to point to its  <a href="..\ndkpi\ns-ndkpi-_ndk_mr_dispatch.md">NDK_MR_DISPATCH</a> table before returning the  created MR object. Also, the NDK provider must not use the <b>Dispatch</b> member after setting it because the NDK consumer can change the <b>Dispatch</b> member to some other value.




## -see-also

<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>



<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_mr_dispatch.md">NDK_MR_DISPATCH</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_mr.md">NDK_FN_CREATE_MR</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_object_header.md">NDK_OBJECT_HEADER</a>



 

 


