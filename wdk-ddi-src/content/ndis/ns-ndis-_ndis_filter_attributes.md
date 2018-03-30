---
UID: NS:ndis._NDIS_FILTER_ATTRIBUTES
title: "_NDIS_FILTER_ATTRIBUTES"
author: windows-driver-content
description: The NDIS_FILTER_ATTRIBUTES structure defines the attributes of a filter module.
old-location: netvista\ndis_filter_attributes.htm
old-project: netvista
ms.assetid: a377d809-4a6f-413e-a26a-446b4eca85ab
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_FILTER_ATTRIBUTES, NDIS_FILTER_ATTRIBUTES, NDIS_FILTER_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], PNDIS_FILTER_ATTRIBUTES, PNDIS_FILTER_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], _NDIS_FILTER_ATTRIBUTES, filter_structures_ref_8711cb33-bba0-41ba-912b-af351c7e758d.xml, ndis/NDIS_FILTER_ATTRIBUTES, ndis/PNDIS_FILTER_ATTRIBUTES, netvista.ndis_filter_attributes"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NDIS_FILTER_ATTRIBUTES
product: Windows
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
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_FILTER_ATTRIBUTES structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
