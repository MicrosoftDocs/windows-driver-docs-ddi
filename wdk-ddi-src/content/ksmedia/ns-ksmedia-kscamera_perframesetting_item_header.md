---
UID: NS:ksmedia.__unnamed_struct_129
title: KSCAMERA_PERFRAMESETTING_ITEM_HEADER (ksmedia.h)
description: This structure contains the header information for a per-frame settings item.
old-location: stream\kscamera_perframesetting_item_header.htm
tech.root: stream
ms.assetid: A550E674-50CA-4956-8422-16875E29D04B
ms.date: 04/30/2019
keywords: ["KSCAMERA_PERFRAMESETTING_ITEM_HEADER structure"]
ms.keywords: "*PKSCAMERA_PERFRAMESETTING_ITEM_HEADER, KSCAMERA_PERFRAMESETTING_ITEM_HEADER, KSCAMERA_PERFRAMESETTING_ITEM_HEADER structure [Streaming Media Devices], PKSCAMERA_PERFRAMESETTING_ITEM_HEADER, PKSCAMERA_PERFRAMESETTING_ITEM_HEADER structure pointer [Streaming Media Devices], ksmedia/KSCAMERA_PERFRAMESETTING_ITEM_HEADER, ksmedia/PKSCAMERA_PERFRAMESETTING_ITEM_HEADER, stream.kscamera_perframesetting_item_header"
f1_keywords:
 - "ksmedia/KSCAMERA_PERFRAMESETTING_ITEM_HEADER"
 - "KSCAMERA_PERFRAMESETTING_ITEM_HEADER"
req.header: ksmedia.h
req.include-header: 
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
- Ksmedia.h
api_name:
- KSCAMERA_PERFRAMESETTING_ITEM_HEADER
targetos: Windows
req.typenames: KSCAMERA_PERFRAMESETTING_ITEM_HEADER, *PKSCAMERA_PERFRAMESETTING_ITEM_HEADER
---

# KSCAMERA_PERFRAMESETTING_ITEM_HEADER structure


## -description


This structure contains the header information for a per-frame settings item.


## -struct-fields




### -field Size

The size of this header and the item payload that follows.


### -field Type

This contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-kscamera_perframesetting_item_type">KSCAMERA_PERFRAMESETTING_ITEM_TYPE</a> structure.


### -field Flags

This is any one of the capability flags reported in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-kscamera_perframesetting_cap_item_header">KSCAMERA_PERFRAMESETTING_CAP_ITEM_HEADER</a> Flags field.

