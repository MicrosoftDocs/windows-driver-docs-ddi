---
UID: NF:ndis.NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO_EX
title: NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO_EX macro
author: windows-driver-content
description: The NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO_EX macro removes a media-specific information data structure from a linked list of such structures that are associated with a NET_BUFFER_LIST structure.
ms.assetid: 4810f8df-a629-43a0-8527-d1baeba17b8a
ms.author: windowsdriverdev
ms.date: 04/13/2018
ms.topic: macro
ms.keywords: NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO_EX
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
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ndis.h
api_name: 
-	NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO_EX
product: Windows
targetos: Windows

---

# NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO_EX macro


## -description

The **NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO_EX** macro removes a media-specific information data structure from a linked list of such structures that are associated with a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure.

## -parameters

### -param _NBL

A pointer to a **NET_BUFFER_LIST** structure.

### -param _MediaSpecificInfo

A pointer to an [**NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX**](ns-ndis-_ndis_nbl_media_specific_information_ex.md) structure that has a **Tag** member matching the **Tag** member of the information structure that should be removed.

## -returns

This macro does not return a value.

## -remarks

Any NDIS 6.20 driver can use **NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO_EX** to remove an [**NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX**](ns-ndis-_ndis_nbl_media_specific_information_ex.md) structure from a list of media-specific information. To specify the type information to remove, specify an **NDIS_NBL_MEDIA_SPECIFIC_INFORMATION_EX** structure with a matching **Tag** member in the *\_MediaSpecificInfo* parameter.

## -see-also

[**NDIS_NBL_REMOVE_MEDIA_SPECIFIC_INFO**](nf-ndis-ndis_nbl_get_media_specific_info.md)

[**NDIS_NBL_MEDIA_SPECIFIC_INFORMATION**](ns-ndis-_ndis_nbl_media_specific_information_ex.md)

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)