---
UID: NS:ndkpi._NDK_ADAPTER
title: "_NDK_ADAPTER"
author: windows-driver-content
description: The NDK_ADAPTER structure specifies the attributes of an NDK adapter object.
old-location: netvista\ndk_adapter.htm
old-project: netvista
ms.assetid: 7EEFC371-5E6F-4507-BF7F-66A1954C7A1A
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , ,, A, D, E, K, N, NDK_ADAPTER, NDK_ADAPTER structure [Network Drivers Starting with Windows Vista], P, PNDK_ADAPTER, PNDK_ADAPTER structure pointer [Network Drivers Starting with Windows Vista], R, T, _, _NDK_ADAPTER, ndkpi/NDK_ADAPTER, ndkpi/PNDK_ADAPTER, netvista.ndk_adapter"
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
-	NDK_ADAPTER
product: Windows
targetos: Windows
req.typenames: NDK_ADAPTER, NDK_ADAPTER
---

# _NDK_ADAPTER structure


## -description


The <b>NDK_ADAPTER</b> structure specifies the attributes of an NDK adapter object.


## -syntax


````
typedef struct _NDK_ADAPTER {
  NDK_OBJECT_HEADER          Header;
  CONST NDK_ADAPTER_DISPATCH *Dispatch;
} NDK_ADAPTER, *PNDK_ADAPTER;
````


## -struct-fields




### -field Header

The <a href="..\ndkpi\ns-ndkpi-_ndk_object_header.md">NDK_OBJECT_HEADER</a> structure for the <b>NDK_ADAPTER</b> structure. Set the <b>ObjectType</b> member of the structure that <b>Header</b> specifies to <b>NdkObjectTypeAdapter</b>.


### -field Dispatch

A pointer to an <a href="..\ndkpi\ns-ndkpi-_ndk_adapter_dispatch.md">NDK_ADAPTER_DISPATCH</a> structure that defines dispatch functions for the NDK adapter object.


## -remarks



The <b>NDK_ADAPTER</b> structure defines an adapter object.  The <a href="..\ndisndk\nc-ndisndk-open_ndk_adapter_handler.md">OPEN_NDK_ADAPTER_HANDLER</a> function opens an NDK adapter instance on an NDK-capable NDIS miniport adapter.

An NDK provider must set the <b>Dispatch</b> member to point to its  <a href="..\ndkpi\ns-ndkpi-_ndk_adapter_dispatch.md">NDK_ADAPTER_DISPATCH</a> table before returning the  created adapter object. Also, the NDK provider must not use the <b>Dispatch</b> member after setting it because the NDK consumer can change the <b>Dispatch</b> member to some other value.




## -see-also

<a href="..\ndisndk\nc-ndisndk-close_ndk_adapter_handler.md">CLOSE_NDK_ADAPTER_HANDLER</a>



<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_adapter_dispatch.md">NDK_ADAPTER_DISPATCH</a>



<a href="..\ndisndk\nc-ndisndk-open_ndk_adapter_handler.md">OPEN_NDK_ADAPTER_HANDLER</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_object_header.md">NDK_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_ADAPTER structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

