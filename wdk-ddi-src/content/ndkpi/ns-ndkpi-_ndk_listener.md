---
UID: NS:ndkpi._NDK_LISTENER
title: "_NDK_LISTENER"
author: windows-driver-content
description: The NDK_LISTENER structure specifies the attributes of an NDK listener object.
old-location: netvista\ndk_listener.htm
old-project: netvista
ms.assetid: 0043DC3F-E8EE-448F-B381-C67C199CE7A7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: NDK_LISTENER, NDK_LISTENER structure [Network Drivers Starting with Windows Vista], PNDK_LISTENER, PNDK_LISTENER structure pointer [Network Drivers Starting with Windows Vista], _NDK_LISTENER, ndkpi/NDK_LISTENER, ndkpi/PNDK_LISTENER, netvista.ndk_listener
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
-	NDK_LISTENER
product: Windows
targetos: Windows
req.typenames: NDK_LISTENER, NDK_LISTENER
---

# _NDK_LISTENER structure


## -description


The <b>NDK_LISTENER</b> structure specifies the attributes of an NDK listener object.


## -syntax


````
typedef struct _NDK_LISTENER {
  NDK_OBJECT_HEADER           Header;
  CONST NDK_LISTENER_DISPATCH *Dispatch;
} NDK_LISTENER, *PNDK_LISTENER;
````


## -struct-fields




### -field Header

The <a href="..\ndkpi\ns-ndkpi-_ndk_object_header.md">NDK_OBJECT_HEADER</a> structure for the <b>NDK_LISTENER</b> structure. Set the <b>ObjectType</b> member of the structure that <b>Header</b> specifies to <b>NdkObjectTypeListener</b>.


### -field Dispatch

A pointer to an <a href="..\ndkpi\ns-ndkpi-_ndk_listener_dispatch.md">NDK_LISTENER_DISPATCH</a> structure that defines dispatch functions for the NDK listener object.


## -remarks



An NDK provider must set the <b>Dispatch</b> member to point to its  <a href="..\ndkpi\ns-ndkpi-_ndk_listener_dispatch.md">NDK_LISTENER_DISPATCH</a> table before returning the  created listener object. Also, the NDK provider must not use the <b>Dispatch</b> member after setting it because the NDK consumer can change the <b>Dispatch</b> member to some other value.




## -see-also

<a href="..\ndkpi\ns-ndkpi-_ndk_listener_dispatch.md">NDK_LISTENER_DISPATCH</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>



<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>



<a href="https://msdn.microsoft.com/956D3550-11C8-48D0-BCF4-9027515C7C0E">NDKPI Listeners, Connectors, and Endpoints</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_listener.md">NDK_FN_CREATE_LISTENER</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_object_header.md">NDK_OBJECT_HEADER</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_LISTENER structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

