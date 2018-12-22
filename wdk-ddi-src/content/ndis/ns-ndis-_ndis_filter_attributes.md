---
UID: NS:ndis._NDIS_FILTER_ATTRIBUTES
title: "_NDIS_FILTER_ATTRIBUTES"
description: The NDIS_FILTER_ATTRIBUTES structure defines the attributes of a filter module.
old-location: netvista\ndis_filter_attributes.htm
tech.root: netvista
ms.assetid: a377d809-4a6f-413e-a26a-446b4eca85ab
ms.date: 05/02/2018
ms.keywords: "*PNDIS_FILTER_ATTRIBUTES, NDIS_FILTER_ATTRIBUTES, NDIS_FILTER_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], PNDIS_FILTER_ATTRIBUTES, PNDIS_FILTER_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], _NDIS_FILTER_ATTRIBUTES, filter_structures_ref_8711cb33-bba0-41ba-912b-af351c7e758d.xml, ndis/NDIS_FILTER_ATTRIBUTES, ndis/PNDIS_FILTER_ATTRIBUTES, netvista.ndis_filter_attributes"
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NDIS_FILTER_ATTRIBUTES
product:
- Windows
targetos: Windows
req.typenames: NDIS_FILTER_ATTRIBUTES, *PNDIS_FILTER_ATTRIBUTES
---

# _NDIS_FILTER_ATTRIBUTES structure


## -description


The NDIS_FILTER_ATTRIBUTES structure defines the attributes of a filter module.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     filter attributes structure (NDIS_FILTER_ATTRIBUTES). Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_FILTER_ATTRIBUTES, the 
     <b>Revision</b> member to NDIS_FILTER_ATTRIBUTES_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_FILTER_ATTRIBUTES_REVISION_1.


### -field Flags

Reserved. Set this member to zero.


## -remarks



A filter drivers passes an NDIS_FILTER_ATTRIBUTES structure to the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562619">NdisFSetAttributes</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562619">NdisFSetAttributes</a>
 

 

