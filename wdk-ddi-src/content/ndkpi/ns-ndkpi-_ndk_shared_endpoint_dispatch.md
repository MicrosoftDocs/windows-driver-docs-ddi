---
UID: NS:ndkpi._NDK_SHARED_ENDPOINT_DISPATCH
title: "_NDK_SHARED_ENDPOINT_DISPATCH"
author: windows-driver-content
description: The NDK_SHARED_ENDPOINT_DISPATCH structure specifies dispatch function entry points for the NDK shared endpoint object.
old-location: netvista\ndk_shared_endpoint_dispatch.htm
old-project: netvista
ms.assetid: A0AFCF2B-E1A9-478C-8B03-D7C873F83369
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "_NDK_SHARED_ENDPOINT_DISPATCH, NDK_SHARED_ENDPOINT_DISPATCH structure [Network Drivers Starting with Windows Vista], netvista.ndk_shared_endpoint_dispatch, NDK_SHARED_ENDPOINT_DISPATCH, ndkpi/NDK_SHARED_ENDPOINT_DISPATCH"
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
-	NDK_SHARED_ENDPOINT_DISPATCH
product: Windows
targetos: Windows
req.typenames: NDK_SHARED_ENDPOINT_DISPATCH
---

# _NDK_SHARED_ENDPOINT_DISPATCH structure


## -description


The <b>NDK_SHARED_ENDPOINT_DISPATCH</b> structure specifies dispatch function entry points for the NDK shared endpoint object.


## -syntax


````
typedef struct _NDK_SHARED_ENDPOINT_DISPATCH {
  NDK_FN_CLOSE_OBJECT                      NdkCloseSharedEndpoint;
  NDK_FN_QUERY_EXTENSION_INTERFACE         NdkQueryExtension;
  NDK_FN_GET_SHARED_ENDPOINT_LOCAL_ADDRESS NdkGetLocalAddress;
} NDK_SHARED_ENDPOINT_DISPATCH;
````


## -struct-fields




### -field NdkCloseSharedEndpoint

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a> dispatch function.


### -field NdkQueryExtension

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_query_extension_interface.md">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.


### -field NdkGetLocalAddress

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_get_shared_endpoint_local_address.md">NDK_FN_GET_SHARED_ENDPOINT_LOCAL_ADDRESS</a> dispatch function.


## -remarks


The <b>NDK_SHARED_ENDPOINT_DISPATCH</b> structure is used in the <a href="..\ndkpi\ns-ndkpi-_ndk_shared_endpoint.md">NDK_SHARED_ENDPOINT</a> structure.



## -see-also

<a href="..\ndkpi\nc-ndkpi-ndk_fn_get_shared_endpoint_local_address.md">NDK_FN_GET_SHARED_ENDPOINT_LOCAL_ADDRESS</a>

<a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_shared_endpoint.md">NDK_SHARED_ENDPOINT</a>

<a href="..\ndkpi\nc-ndkpi-ndk_fn_query_extension_interface.md">NDK_FN_QUERY_EXTENSION_INTERFACE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_SHARED_ENDPOINT_DISPATCH structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

