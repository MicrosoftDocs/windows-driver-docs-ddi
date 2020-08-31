---
UID: NS:ndis._NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX
title: _NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX (ndis.h)
description: The NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structure defines media-specific information that is associated with a NET_BUFFER_LIST structure.
old-location: netvista\ndis_nbl_media_specific_information_ex.htm
tech.root: netvista
ms.assetid: f2c74fc3-45e2-4541-81a1-eb022e24cede
ms.date: 05/02/2018
keywords: ["NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structure"]
ms.keywords: "*PNDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX, NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX, NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structure [Network Drivers Starting with Windows Vista], PNDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX, PNDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX, ndis/NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX, ndis/PNDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX, ndis_netbuf_macros_media_specific_587542fc-f693-4a93-b343-0a9e86e6659e.xml, netvista.ndis_nbl_media_specific_information_ex"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
targetos: Windows
req.typenames: NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX, *PNDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX
f1_keywords:
 - _NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX
 - ndis/_NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX
 - PNDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX
 - ndis/PNDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX
 - NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX
 - ndis/NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX
---

# _NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structure


## -description

The <b>NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX</b> structure defines media-specific information that is
  associated with a 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure.

## -struct-fields

### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     structure (NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX). The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_NBL_MEDIA_SPECIFIC_INFO_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_NBL_MEDIA_SPECIFIC_INFO_REVISION_1.

### -field NextEntry

A pointer to the next NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structure in a linked list of
     NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structures. If this is the last structure in the list, the
     pointer is <b>NULL</b>. Drivers must use the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_nbl_media_specific_information_ex">
     NDIS_NBL_ADD_MEDIA_SPECIFIC_INFO_EX</a>, 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-nbl-get-media-specific-info-ex">
     NDIS_NBL_GET_MEDIA_SPECIFIC_INFO_EX</a>, and 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_nbl_media_specific_information_ex">
     NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO_EX</a> macros to manipulate this list.

### -field Tag

A unique value (assigned by Microsoft) that identifies the type of media-specific information.
     This member is reserved for system use.
     

New tags can be assigned in future system releases for new media types that require additional OOB
     data specific to a particular media type.

### -field Data

A pointer to a buffer that contains the media-specific information.

## -remarks

NDIS 6.20 and later drivers should use the NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structure to specify
    media-specific information. Any driver in an NDIS driver stack can allocate and manage media-specific
    information. The media-specific information is specified in a NULL-terminated linked list of
    NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structures, and each structure contains driver-allocated and
    driver-defined data.

Structures in the list contain any media-specific out-of-band (OOB) data that accompanies the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures that are associated with a 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure.

If a protocol driver allocated the OOB data, it configured the data for a send operation. If a
    miniport driver allocated the data, it configured the data for a receive indication.

To get the first element in the linked list, an NDIS driver calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-list-info">NET_BUFFER_LIST_INFO</a> macro and specifies
    the 
    <b>MediaSpecificInformationEx</b> information type.

To add, get, and remove NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX structures in the linked list, use the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_nbl_media_specific_information_ex">
    NDIS_NBL_ADD_MEDIA_SPECIFIC_INFO_EX</a>, 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-nbl-get-media-specific-info-ex">
    NDIS_NBL_GET_MEDIA_SPECIFIC_INFO_EX</a>, and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_nbl_media_specific_information_ex">
    NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO_EX</a> macros.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_nbl_media_specific_information_ex">
   NDIS_NBL_ADD_MEDIA_SPECIFIC_INFO_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-nbl-get-media-specific-info-ex">
   NDIS_NBL_GET_MEDIA_SPECIFIC_INFO_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_nbl_media_media_specific_information">NDIS_NBL_MEDIA_SPECIFIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_nbl_media_specific_information_ex">
   NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-list-info">NET_BUFFER_LIST_INFO</a>

