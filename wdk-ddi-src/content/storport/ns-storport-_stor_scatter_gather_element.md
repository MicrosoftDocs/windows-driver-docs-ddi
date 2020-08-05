---
UID: NS:storport._STOR_SCATTER_GATHER_ELEMENT
title: _STOR_SCATTER_GATHER_ELEMENT (storport.h)
description: The STOR_SCATTER_GATHER_ELEMENT structure is used with STOR_SCATTER_GATHER_LIST to build a list of scatter/gather elements.
old-location: storage\stor_scatter_gather_element.htm
tech.root: storage
ms.assetid: 2e387418-a37c-492b-8ee4-b6ff8f0e53b0
ms.date: 03/29/2018
keywords: ["STOR_SCATTER_GATHER_ELEMENT structure"]
ms.keywords: "*PSTOR_SCATTER_GATHER_ELEMENT, PSTOR_SCATTER_GATHER_ELEMENT, PSTOR_SCATTER_GATHER_ELEMENT structure pointer [Storage Devices], STOR_SCATTER_GATHER_ELEMENT, STOR_SCATTER_GATHER_ELEMENT structure [Storage Devices], _STOR_SCATTER_GATHER_ELEMENT, storage.stor_scatter_gather_element, storport/PSTOR_SCATTER_GATHER_ELEMENT, storport/STOR_SCATTER_GATHER_ELEMENT, structs-storport_e7e71caf-d421-45ba-b356-c1450eec6e6c.xml"
f1_keywords:
 - "storport/STOR_SCATTER_GATHER_ELEMENT"
 - "STOR_SCATTER_GATHER_ELEMENT"
req.header: storport.h
req.include-header: Storport.h
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
- storport.h
api_name:
- STOR_SCATTER_GATHER_ELEMENT
targetos: Windows
req.typenames: STOR_SCATTER_GATHER_ELEMENT, *PSTOR_SCATTER_GATHER_ELEMENT
---

# _STOR_SCATTER_GATHER_ELEMENT structure


## -description


The STOR_SCATTER_GATHER_ELEMENT structure is used with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_stor_scatter_gather_list">STOR_SCATTER_GATHER_LIST</a> to build a list of scatter/gather elements. 


## -struct-fields




### -field PhysicalAddress

Contains the physical address of the scatter/gather element. 


### -field Length

Contains the length in bytes of this scatter/gather element. 


### -field Reserved

Reserved. 


## -remarks



Miniport drivers used with the Storport driver retrieve an array of these structures using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportgetscattergatherlist">StorPortGetScatterGatherList</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_stor_scatter_gather_list">STOR_SCATTER_GATHER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportgetscattergatherlist">StorPortGetScatterGatherList</a>
 

 

