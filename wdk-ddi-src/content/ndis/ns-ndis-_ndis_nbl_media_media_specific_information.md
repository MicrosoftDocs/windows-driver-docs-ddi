---
UID: NS:ndis._NDIS_NBL_MEDIA_MEDIA_SPECIFIC_INFORMATION
title: "_NDIS_NBL_MEDIA_MEDIA_SPECIFIC_INFORMATION"
author: windows-driver-content
description: The NDIS_NBL_MEDIA_SPECIFIC_INFORMATION structure specifies media-specific data that is associated with a NET_BUFFER_LIST structure.
old-location: netvista\ndis_nbl_media_specific_information.htm
tech.root: netvista
ms.assetid: 01c0d9bb-5935-4b61-a04d-f9fcc5457152
ms.date: 5/2/2018
ms.keywords: "*PNDIS_NBL_MEDIA_SPECIFIC_INFORMATION, NDIS_NBL_MEDIA_SPECIFIC_INFORMATION, NDIS_NBL_MEDIA_SPECIFIC_INFORMATION structure [Network Drivers Starting with Windows Vista], PNDIS_NBL_MEDIA_SPECIFIC_INFORMATION, PNDIS_NBL_MEDIA_SPECIFIC_INFORMATION structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NBL_MEDIA_MEDIA_SPECIFIC_INFORMATION, ndis/NDIS_NBL_MEDIA_SPECIFIC_INFORMATION, ndis/PNDIS_NBL_MEDIA_SPECIFIC_INFORMATION, ndis_netbuf_structures_ref_d272f589-0af5-458e-8238-5ba58858ccc0.xml, netvista.ndis_nbl_media_specific_information"
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and 6.1. For NDIS 6.20 and later, use NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX.
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
-	NDIS_NBL_MEDIA_SPECIFIC_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: NDIS_NBL_MEDIA_SPECIFIC_INFORMATION, *PNDIS_NBL_MEDIA_SPECIFIC_INFORMATION
---

# _NDIS_NBL_MEDIA_MEDIA_SPECIFIC_INFORMATION structure


## -description


The NDIS_NBL_MEDIA_SPECIFIC_INFORMATION structure specifies media-specific data that is associated
  with a 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.


## -struct-fields




### -field NextEntry

A pointer to the next media-specific information structure in a linked list.


### -field Tag

A unique pre-assigned value that identifies the type of the media-specific information. This
     member is reserved for system use.
     

New tags can be assigned in future system releases for new media types that require additional OOB
     data specific to a particular media type.


### -field Data

A variable sized UCHAR array that contains the media-specific information.


## -remarks



Any driver in an NDIS driver stack can allocate and manage media-specific information. The
    media-specific information is in a linked list of NDIS_NBL_MEDIA_SPECIFIC_INFORMATION structures that
    contain driver-allocated and driver-defined data. Structures in the list contain any media-specific
    out-of-band (OOB) data that accompanies the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures associated with a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.

If a protocol driver allocated the OOB data, it configured the data for a send operation. If a
    miniport driver allocated the data, it configured the data for a receive indication.

To access NDIS_NBL_MEDIA_SPECIFIC_INFORMATION structures in a linked list, use the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff566503">
    NDIS_NBL_ADD_MEDIA_SPECIFIC_INFO</a>, 
    <a href="https://msdn.microsoft.com/library/gg159261.aspx">
    NDIS_NBL_GET_MEDIA_SPECIFIC_INFO</a>, and 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff566520">
    NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO</a> macros.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566503">
   NDIS_NBL_ADD_MEDIA_SPECIFIC_INFO</a>



<a href="https://msdn.microsoft.com/library/gg159261.aspx">
   NDIS_NBL_GET_MEDIA_SPECIFIC_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566518">NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566520">
   NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>
 

 

