---
UID: NF:ndis.NDIS_NBL_ADD_MEDIA_SPECIFIC_INFO_EX
title: NDIS_NBL_ADD_MEDIA_SPECIFIC_INFO_EX macro (ndis.h)
description: The NDIS_NBL_ADD_MEDIA_SPECIFIC_INFO_EX macro adds a media-specific information data structure to the beginning of a linked list of such structures that are associated with a NET_BUFFER_LIST structure.
tech.root: netvista
ms.assetid: aa089b07-e623-44c1-9f2e-ee256d7bef16
ms.date: 04/13/2018
keywords: ["NDIS_NBL_ADD_MEDIA_SPECIFIC_INFO_EX macro"]
f1_keywords:
 - "ndis/NDIS_NBL_ADD_MEDIA_SPECIFIC_INFO_EX"
ms.keywords: NDIS_NBL_ADD_MEDIA_SPECIFIC_INFO_EX
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
- NDIS_NBL_ADD_MEDIA_SPECIFIC_INFO_EX
product:
- Windows
targetos: Windows

---

# NDIS_NBL_ADD_MEDIA_SPECIFIC_INFO_EX macro


## -description

The **NDIS_NBL_ADD_MEDIA_SPECIFIC_INFO_EX** macro adds a media-specific information data structure to the beginning of a linked list of such structures that are associated with a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

### -param _MediaSpecificInfo

A pointer to an [**NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX**](ns-ndis-_ndis_nbl_media_specific_information_ex.md) structure to add to the linked list.

## -remarks

Any NDIS 6.20 or later driver can use **NDIS_NBL_ADD_MEDIA_SPECIFIC_INFO_EX** to add media-specific information to a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -see-also

[**NDIS_NBL_ADD_MEDIA_SPECIFIC_INFO**](nf-ndis-ndis_nbl_add_media_specific_info.md)

[**NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX**](ns-ndis-_ndis_nbl_media_specific_information_ex.md)

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)
