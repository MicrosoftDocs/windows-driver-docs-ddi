---
UID: NF:ndis.NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO
title: NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO macro (ndis.h)
description: The NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO macro removes a media-specific information data structure from a linked list of such structures that are associated with a NET_BUFFER_LIST structure.
tech.root: netvista
ms.assetid: 4434561f-23f4-454c-9396-2e87b7aa322c
ms.date: 04/13/2018
keywords: ["NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO macro"]
ms.keywords: NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO
req.header: ndis.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and 6.1. For NDIS 6.20 and later, use NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO_EX.
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
targetos: Windows
f1_keywords:
 - NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO
 - ndis/NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO
---

# NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO macro


## -description

> [!IMPORTANT]
> This macro is supported in NDIS 6.0 and 6.1. For NDIS 6.20 and later, use [**NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO_EX**](nf-ndis-ndis_nbl_remove_media_specific_info_ex.md).

The **NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO** macro removes a media-specific information data structure from a linked list of such structures that are associated with a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

### -param _MediaSpecificInfo

A pointer to an [**NDIS_NBL_MEDIA_SPECIFIC_INFORMATION**](ns-ndis-_ndis_nbl_media_media_specific_information.md) structure that has a **Tag** member matching the **Tag** member of the information structure that should be removed.

## -remarks

Any NDIS 6.0 or 6.1 driver can use **NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO** to remove an [**NDIS_NBL_MEDIA_SPECIFIC_INFORMATION**](ns-ndis-_ndis_nbl_media_media_specific_information.md) structure from a list of media-specific information. To specify the type information to remove, specify an **NDIS_NBL_MEDIA_SPECIFIC_INFORMATION** structure with a matching **Tag** member in the *\_MediaSpecificInfo* parameter.

## -see-also

[**NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO_EX**](nf-ndis-ndis_nbl_get_media_specific_info_ex.md)

[**NDIS_NBL_MEDIA_SPECIFIC_INFORMATION**](ns-ndis-_ndis_nbl_media_media_specific_information.md)

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)

