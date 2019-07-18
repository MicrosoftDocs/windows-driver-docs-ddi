---
UID: NS:wmistr.tagWNODE_TOO_SMALL
title: tagWNODE_TOO_SMALL (wmistr.h)
description: The WNODE_TOO_SMALL structure indicates the size of the buffer needed to receive output from a request.
old-location: kernel\wnode_too_small.htm
tech.root: kernel
ms.assetid: eb3d8e2a-20f6-41fc-a220-de93eb83f359
ms.date: 04/30/2018
ms.keywords: "*PWNODE_TOO_SMALL, PWNODE_TOO_SMALL, PWNODE_TOO_SMALL structure pointer [Kernel-Mode Driver Architecture], WNODE_TOO_SMALL, WNODE_TOO_SMALL structure [Kernel-Mode Driver Architecture], kernel.wnode_too_small, kstruct_d_dcabaeb1-21d1-4cbe-a3ea-c6022e57e4b9.xml, tagWNODE_TOO_SMALL, wmistr/PWNODE_TOO_SMALL, wmistr/WNODE_TOO_SMALL"
ms.topic: struct
f1_keywords:
 - "wmistr/WNODE_TOO_SMALL"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wmistr.h
api_name:
- WNODE_TOO_SMALL
product:
- Windows
targetos: Windows
req.typenames: WNODE_TOO_SMALL, *PWNODE_TOO_SMALL
---

# tagWNODE_TOO_SMALL structure


## -description


The <b>WNODE_TOO_SMALL</b> structure indicates the size of the buffer needed to receive output from a request.


## -struct-fields




### -field WnodeHeader

Is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-_wnode_header">WNODE_HEADER</a> structure that contains information common to all <b>WNODE_<i>XXX</i></b> structures, such as the buffer size, the GUID that represents a data block associated with a request, and flags that provide information about the <b>WNODE_<i>XXX</i></b> data being passed or returned.


### -field SizeNeeded

Specifies the size of the buffer needed to receive all of the <b>WNODE_<i>XXX</i></b> data to be returned.


## -remarks



When the buffer for a WMI request is too small to receive all of the data to be returned, a driver fills in a <b>WNODE_TOO_SMALL</b> structure to indicate the required buffer size. WMI can then increase the buffer to the recommended size and issue the request again. A driver is responsible for managing any side effects caused by handling the same request more than once. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-_wnode_header">WNODE_HEADER</a>
 

 

