---
UID: NS:storport._STOR_SCATTER_GATHER_ELEMENT
title: _STOR_SCATTER_GATHER_ELEMENT
author: windows-driver-content
description: The STOR_SCATTER_GATHER_ELEMENT structure is used with STOR_SCATTER_GATHER_LIST to build a list of scatter/gather elements.
old-location: storage\stor_scatter_gather_element.htm
old-project: storage
ms.assetid: 2e387418-a37c-492b-8ee4-b6ff8f0e53b0
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _STOR_SCATTER_GATHER_ELEMENT, STOR_SCATTER_GATHER_ELEMENT, *PSTOR_SCATTER_GATHER_ELEMENT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STOR_SCATTER_GATHER_ELEMENT
req.alt-loc: storport.h
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
req.typenames: STOR_SCATTER_GATHER_ELEMENT, *PSTOR_SCATTER_GATHER_ELEMENT
req.product: Windows 10 or later.
---

# _STOR_SCATTER_GATHER_ELEMENT structure



## -description
The STOR_SCATTER_GATHER_ELEMENT structure is used with <a href="..\storport\ns-storport-_stor_scatter_gather_list.md">STOR_SCATTER_GATHER_LIST</a> to build a list of scatter/gather elements. 



## -syntax

````
typedef struct _STOR_SCATTER_GATHER_ELEMENT {
  STOR_PHYSICAL_ADDRESS PhysicalAddress;
  ULONG                 Length;
  ULONG_PTR             Reserved;
} STOR_SCATTER_GATHER_ELEMENT, *PSTOR_SCATTER_GATHER_ELEMENT;
````


## -struct-fields

### -field PhysicalAddress

Contains the physical address of the scatter/gather element. 


### -field Length

Contains the length in bytes of this scatter/gather element. 


### -field Reserved

Reserved. 


## -remarks
Miniport drivers used with the Storport driver retrieve an array of these structures using <a href="..\storport\nf-storport-storportgetscattergatherlist.md">StorPortGetScatterGatherList</a>. 


## -see-also
<dl>
<dt>
<a href="..\storport\ns-storport-_stor_scatter_gather_list.md">STOR_SCATTER_GATHER_LIST</a>
</dt>
<dt>
<a href="..\storport\nf-storport-storportgetscattergatherlist.md">StorPortGetScatterGatherList</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STOR_SCATTER_GATHER_ELEMENT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

