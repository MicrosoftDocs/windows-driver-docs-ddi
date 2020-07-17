---
UID: NS:storport._STOR_SCATTER_GATHER_LIST
title: _STOR_SCATTER_GATHER_LIST (storport.h)
description: The STOR_SCATTER_GATHER_LIST structure is used in conjunction with the StorPortGetScatterGatherList routine to retrieve the scatter/gather list for a SCSI request block (SRB).
old-location: storage\stor_scatter_gather_list.htm
tech.root: storage
ms.assetid: 9fbb8dea-67d3-4bb9-afc2-d623bea2ca8d
ms.date: 03/29/2018
keywords: ["_STOR_SCATTER_GATHER_LIST structure"]
ms.keywords: "*PSTOR_SCATTER_GATHER_LIST, PSTOR_SCATTER_GATHER_LIST, PSTOR_SCATTER_GATHER_LIST structure pointer [Storage Devices], STOR_SCATTER_GATHER_LIST, STOR_SCATTER_GATHER_LIST structure [Storage Devices], _STOR_SCATTER_GATHER_LIST, storage.stor_scatter_gather_list, storport/PSTOR_SCATTER_GATHER_LIST, storport/STOR_SCATTER_GATHER_LIST, structs-storport_eac06620-81b1-42e8-9517-3a2ce1b6623a.xml"
f1_keywords:
 - "storport/STOR_SCATTER_GATHER_LIST"
 - "STOR_SCATTER_GATHER_LIST"
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
- STOR_SCATTER_GATHER_LIST
product:
- Windows
targetos: Windows
req.typenames: STOR_SCATTER_GATHER_LIST, *PSTOR_SCATTER_GATHER_LIST
---

# _STOR_SCATTER_GATHER_LIST structure


## -description


The STOR_SCATTER_GATHER_LIST structure is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportgetscattergatherlist">StorPortGetScatterGatherList</a> routine to retrieve the scatter/gather list for a SCSI request block (SRB). 


## -struct-fields




### -field NumberOfElements

Contains the number of scatter/gather elements in the list. 


### -field Reserved

Reserved. 


### -field List

Contains the array of scatter/gather elements. 


## -remarks



Miniport drivers that work with the Storport driver call the Storport support routine, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportgetscattergatherlist">StorPortGetScatterGatherList</a>, to retrieve the scatter gather list for an SRB. <b>StorPortGetScatterGatherList</b> returns a structure of type STOR_SCATTER_GATHER_LIST. Each scatter/gather element is of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_stor_scatter_gather_element">STOR_SCATTER_GATHER_ELEMENT</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_stor_scatter_gather_element">STOR_SCATTER_GATHER_ELEMENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportgetscattergatherlist">StorPortGetScatterGatherList</a>
 

 

