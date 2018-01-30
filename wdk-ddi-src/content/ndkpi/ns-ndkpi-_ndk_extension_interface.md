---
UID: NS:ndkpi._NDK_EXTENSION_INTERFACE
title: "_NDK_EXTENSION_INTERFACE"
author: windows-driver-content
description: The NDK_EXTENSION_INTERFACE structure specifies dispatch function entry points for an NDK extension interface.
old-location: netvista\ndk_extension_interface.htm
old-project: netvista
ms.assetid: BFA8FF36-1B10-4358-8826-9D5C32F27CFF
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndkpi/PNDK_EXTENSION_INTERFACE, ndkpi/NDK_EXTENSION_INTERFACE, NDK_EXTENSION_INTERFACE, PNDK_EXTENSION_INTERFACE structure pointer [Network Drivers Starting with Windows Vista], _NDK_EXTENSION_INTERFACE, PNDK_EXTENSION_INTERFACE, NDK_EXTENSION_INTERFACE structure [Network Drivers Starting with Windows Vista], netvista.ndk_extension_interface
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
-	NDK_EXTENSION_INTERFACE
product: Windows
targetos: Windows
req.typenames: NDK_EXTENSION_INTERFACE
---

# _NDK_EXTENSION_INTERFACE structure


## -description


The <b>NDK_EXTENSION_INTERFACE</b> structure specifies dispatch function entry points for an NDK extension interface.


## -syntax


````
typedef struct _NDK_EXTENSION_INTERFACE {
  const VOID *Dispatch;
} NDK_EXTENSION_INTERFACE, *PNDK_EXTENSION_INTERFACE;
````


## -struct-fields




### -field Dispatch

An entry point for an extension interface dispatch function.


## -remarks


An extension interface is identified by a GUID and represented as a pointer to an <b>NDK_EXTENSION_INTERFACE</b> function dispatch table.

Each NDK object contains a <a href="..\ndkpi\nc-ndkpi-ndk_fn_query_extension_interface.md">NDK_FN_QUERY_EXTENSION_INTERFACE</a> function pointer in its object type-specific function dispatch table. This function allows a driver to query the extended interfaces the object type supports.
<div class="alert"><b>Tip</b>   There are currently no standard extension interfaces defined.</div><div> </div>


## -see-also

<a href="..\ndkpi\nc-ndkpi-ndk_fn_query_extension_interface.md">NDK_FN_QUERY_EXTENSION_INTERFACE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_EXTENSION_INTERFACE structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

