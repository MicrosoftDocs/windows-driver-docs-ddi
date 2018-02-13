---
UID: NS:ndkpi._NDK_CQ
title: "_NDK_CQ"
author: windows-driver-content
description: The NDK_CQ structure specifies the attributes of an NDK completion queue (CQ) object.
old-location: netvista\ndk_cq.htm
old-project: netvista
ms.assetid: FE5E1E5F-3EEC-4FF4-B275-E2B086ADCDCC
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NDK_CQ structure [Network Drivers Starting with Windows Vista], PNDK_CQ structure pointer [Network Drivers Starting with Windows Vista], netvista.ndk_cq, ndkpi/NDK_CQ, PNDK_CQ, ndkpi/PNDK_CQ, _NDK_CQ, NDK_CQ
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
-	NDK_CQ
product: Windows
targetos: Windows
req.typenames: NDK_CQ
---

# _NDK_CQ structure


## -description


The <b>NDK_CQ</b> structure specifies the attributes of an NDK completion queue (CQ) object.


## -syntax


````
typedef struct _NDK_CQ {
  NDK_OBJECT_HEADER     Header;
  CONST NDK_CQ_DISPATCH *Dispatch;
} NDK_CQ, *PNDK_CQ;
````


## -struct-fields




### -field Header

The <a href="..\ndkpi\ns-ndkpi-_ndk_object_header.md">NDK_OBJECT_HEADER</a> structure for the NDK_CQ structure. Set the <b>ObjectType</b> member of the structure that <b>Header</b> specifies to <b>NdkObjectTypeCq</b>.


### -field Dispatch

A pointer to an <a href="..\ndkpi\ns-ndkpi-_ndk_cq_dispatch.md">NDK_CQ_DISPATCH</a> structure that defines dispatch functions for the NDK CQ object.


## -remarks



An NDK provider must set the <b>Dispatch</b> member to point to its  <a href="..\ndkpi\ns-ndkpi-_ndk_cq_dispatch.md">NDK_CQ_DISPATCH</a> table before returning the  created CQ object. Also, the NDK provider must not use the <b>Dispatch</b> member after setting it because the NDK consumer can change the <b>Dispatch</b> member to some other value.




## -see-also

<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>



<a href="https://msdn.microsoft.com/87150E2F-64F2-4EAB-A8B3-8E77622BE36C">NDKPI Completion Handling Requirements</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_cq.md">NDK_FN_CREATE_CQ</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_object_header.md">NDK_OBJECT_HEADER</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_cq_dispatch.md">NDK_CQ_DISPATCH</a>



<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_CQ structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

