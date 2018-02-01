---
UID: NS:ndkpi._NDK_QP
title: "_NDK_QP"
author: windows-driver-content
description: The NDK_QP structure specifies the attributes of an NDK queue pair (QP) object.
old-location: netvista\ndk_qp.htm
old-project: netvista
ms.assetid: 43491796-35CA-4E0C-90EF-7148651C68A6
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NDK_QP, _NDK_QP, netvista.ndk_qp, ndkpi/NDK_QP, NDK_QP structure [Network Drivers Starting with Windows Vista]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndkpi.h
apiname:
-	NDK_QP
product: Windows
targetos: Windows
req.typenames: NDK_QP
---

# _NDK_QP structure


## -description


The <b>NDK_QP</b> structure specifies the attributes of an NDK queue pair (QP) object.


## -syntax


````
typedef struct _NDK_QP {
  NDK_OBJECT_HEADER     Header;
  CONST NDK_QP_DISPATCH *Dispatch;
} NDK_QP;
````


## -struct-fields




### -field Header

The <a href="..\ndkpi\ns-ndkpi-_ndk_object_header.md">NDK_OBJECT_HEADER</a> structure for the <b>NDK_QP</b> structure. Set the <b>ObjectType</b> member of the structure that <b>Header</b> specifies to <b>NdkObjectTypeQp</b>.


### -field Dispatch

A pointer to an <a href="..\ndkpi\ns-ndkpi-_ndk_qp_dispatch.md">NDK_QP_DISPATCH</a> structure that defines dispatch functions for the NDK QP object.


## -remarks


An NDK provider must set the <b>Dispatch</b> member to point to its  <a href="..\ndkpi\ns-ndkpi-_ndk_qp_dispatch.md">NDK_QP_DISPATCH</a> table before returning the  created QP object. Also, the NDK provider must not use the <b>Dispatch</b> member after setting it because the NDK consumer can change the <b>Dispatch</b> member to some other value.



## -see-also

<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_qp_with_srq.md">NDK_FN_CREATE_QP_WITH_SRQ</a>

<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_qp.md">NDK_FN_CREATE_QP</a>

<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>

<a href="https://msdn.microsoft.com/2BF6F253-FCB4-4A61-9A67-81092F3C44E4">NDKPI Work Request Posting Requirements</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_qp_dispatch.md">NDK_QP_DISPATCH</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_object_header.md">NDK_OBJECT_HEADER</a>

<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>

<a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_QP structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

