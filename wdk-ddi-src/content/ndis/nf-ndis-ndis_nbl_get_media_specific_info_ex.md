---
UID: NF:ndis.NDIS_NBL_GET_MEDIA_SPECIFIC_INFO_EX
title: NDIS_NBL_GET_MEDIA_SPECIFIC_INFO_EX macro (ndis.h)
description: The NDIS_NBL_GET_MEDIA_SPECIFIC_INFO_EX macro gets a media-specific information data structure from a linked list of such structures that are associated with a NET_BUFFER_LIST structure.
tech.root: netvista
ms.assetid: fb67b64f-e91a-4e9d-8576-6ad7db979fbc
ms.date: 04/13/2018
ms.topic: macro
f1_keywords:
 - "ndis/NDIS_NBL_GET_MEDIA_SPECIFIC_INFO_EX"
ms.keywords: NDIS_NBL_GET_MEDIA_SPECIFIC_INFO_EX
req.header: ndis.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ndis.h
api_name: 
- NDIS_NBL_GET_MEDIA_SPECIFIC_INFO_EX
product:
- Windows
targetos: Windows

---

# NDIS_NBL_GET_MEDIA_SPECIFIC_INFO_EX macro


## -description

The **NDIS_NBL_GET_MEDIA_SPECIFIC_INFO_EX** macro gets a media-specific information data structure from a linked list of such structures that are associated with a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

### -param _Tag

A unique pre-assigned value that identifies the type of the media-specific information.

New tags can be assigned in future system releases for new media types that require additional OOB data specific to a particular media type.

### -param _MediaSpecificInfo

A pointer to an [**NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX**](ns-ndis-_ndis_nbl_media_specific_information_ex.md) structure.

## -remarks

Any NDIS 6.20 driver can use **NDIS_NBL_GET_MEDIA_SPECIFIC_INFO_EX** to get media-specific information from a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure. When this macro returns, the *\_MediaSpecificInfo* parameter contains a pointer to the first [**NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX**](ns-ndis-_ndis_nbl_media_specific_information_ex.md) structure in the media-specific information list that has a **Tag** member matching the value specified in the *\_Tag* parameter.

## -see-also

[**NDIS_NBL_GET_MEDIA_SPECIFIC_INFO**](nf-ndis-ndis_nbl_get_media_specific_info.md)

[**NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX**](ns-ndis-_ndis_nbl_media_specific_information_ex.md)

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)
