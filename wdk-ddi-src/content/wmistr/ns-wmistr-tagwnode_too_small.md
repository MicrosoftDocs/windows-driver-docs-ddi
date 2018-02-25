---
UID: NS:wmistr.tagWNODE_TOO_SMALL
title: tagWNODE_TOO_SMALL
author: windows-driver-content
description: The WNODE_TOO_SMALL structure indicates the size of the buffer needed to receive output from a request.
old-location: kernel\wnode_too_small.htm
old-project: kernel
ms.assetid: eb3d8e2a-20f6-41fc-a220-de93eb83f359
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PWNODE_TOO_SMALL, ,, A, D, E, L, M, N, O, P, PWNODE_TOO_SMALL, PWNODE_TOO_SMALL structure pointer [Kernel-Mode Driver Architecture], S, T, W, WNODE_TOO_SMALL, WNODE_TOO_SMALL structure [Kernel-Mode Driver Architecture], _, a, g, kernel.wnode_too_small, kstruct_d_dcabaeb1-21d1-4cbe-a3ea-c6022e57e4b9.xml, t, tagWNODE_TOO_SMALL, wmistr/PWNODE_TOO_SMALL, wmistr/WNODE_TOO_SMALL"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wmistr.h
req.include-header: Wmistr.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wmistr.h
apiname:
-	WNODE_TOO_SMALL
product: Windows
targetos: Windows
req.typenames: WNODE_TOO_SMALL, *PWNODE_TOO_SMALL
req.product: Windows 10 or later.
---

# tagWNODE_TOO_SMALL structure


## -description


The <b>WNODE_TOO_SMALL</b> structure indicates the size of the buffer needed to receive output from a request.


## -syntax


````
typedef struct tagWNODE_TOO_SMALL {
  struct _WNODE_HEADER  WnodeHeader;
  ULONG                SizeNeeded;
} WNODE_TOO_SMALL, *PWNODE_TOO_SMALL;
````


## -struct-fields




### -field WnodeHeader

Is a <a href="..\wmistr\ns-wmistr-_wnode_header.md">WNODE_HEADER</a> structure that contains information common to all <b>WNODE_<i>XXX</i></b> structures, such as the buffer size, the GUID that represents a data block associated with a request, and flags that provide information about the <b>WNODE_<i>XXX</i></b> data being passed or returned.


### -field SizeNeeded

Specifies the size of the buffer needed to receive all of the <b>WNODE_<i>XXX</i></b> data to be returned.


## -remarks



When the buffer for a WMI request is too small to receive all of the data to be returned, a driver fills in a <b>WNODE_TOO_SMALL</b> structure to indicate the required buffer size. WMI can then increase the buffer to the recommended size and issue the request again. A driver is responsible for managing any side effects caused by handling the same request more than once. 




## -see-also

<a href="..\wmistr\ns-wmistr-_wnode_header.md">WNODE_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20WNODE_TOO_SMALL structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

