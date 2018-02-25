---
UID: NS:ndkpi._NDK_SRQ
title: "_NDK_SRQ"
author: windows-driver-content
description: The NDK_SRQ structure specifies the attributes of an NDK shared receive queue (SRQ) object.
old-location: netvista\ndk_srq.htm
old-project: netvista
ms.assetid: BDD2E8A6-D233-4581-AC1D-B6E33919898E
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , ,, D, K, N, NDK_SRQ, NDK_SRQ structure [Network Drivers Starting with Windows Vista], PNDK_SRQ, PNDK_SRQ structure pointer [Network Drivers Starting with Windows Vista], Q, R, S, _, _NDK_SRQ, ndkpi/NDK_SRQ, ndkpi/PNDK_SRQ, netvista.ndk_srq"
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
-	NDK_SRQ
product: Windows
targetos: Windows
req.typenames: NDK_SRQ, NDK_SRQ
---

# _NDK_SRQ structure


## -description


The <b>NDK_SRQ</b> structure specifies the attributes of an NDK shared receive queue (SRQ) object.


## -syntax


````
typedef struct _NDK_SRQ {
  NDK_OBJECT_HEADER      Header;
  CONST NDK_SRQ_DISPATCH *Dispatch;
} NDK_SRQ, *PNDK_SRQ;
````


## -struct-fields




### -field Header

The <a href="..\ndkpi\ns-ndkpi-_ndk_object_header.md">NDK_OBJECT_HEADER</a> structure for the NDK_SRQ structure. Set the <b>ObjectType</b> member of the structure that <b>Header</b> specifies to <b>NdkObjectTypeSrq</b>.


### -field Dispatch

A pointer to an <a href="..\ndkpi\ns-ndkpi-_ndk_srq_dispatch.md">NDK_SRQ_DISPATCH</a> structure that defines dispatch functions for the NDK SRQ object.


## -remarks



An NDK provider must set the <b>Dispatch</b> member to point to its  <a href="..\ndkpi\ns-ndkpi-_ndk_srq_dispatch.md">NDK_SRQ_DISPATCH</a> table before returning the  created SRQ object. Also, the NDK provider must not use the <b>Dispatch</b> member after setting it because the NDK consumer can change the <b>Dispatch</b> member to some other value.




## -see-also

<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_srq.md">NDK_FN_CREATE_SRQ</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_qp_with_srq.md">NDK_FN_CREATE_QP_WITH_SRQ</a>



<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_srq_dispatch.md">NDK_SRQ_DISPATCH</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_object_header.md">NDK_OBJECT_HEADER</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a>



<a href="https://msdn.microsoft.com/2BF6F253-FCB4-4A61-9A67-81092F3C44E4">NDKPI Work Request Posting Requirements</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_SRQ structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

