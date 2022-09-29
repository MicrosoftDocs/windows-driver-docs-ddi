---
UID: NS:acpitabl._MHSP_CHANNEL
tech.root: acpi
title: MHSP_CHANNEL (acpitabl.h)
ms.date: 03/01/2022
targetos: Windows
description: This topic describes the MHSP_CHANNEL structure used by the Microsoft HSP ACPI table.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acpitabl.h
req.include-header: Acpitabl.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: Windows
req.typenames: MHSP_CHANNEL, *PMHSP_CHANNEL
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acpitabl.h
api_name:
 - _MHSP_CHANNEL
 - PMHSP_CHANNEL
 - MHSP_CHANNEL
f1_keywords:
 - _MHSP_CHANNEL
 - acpitabl/_MHSP_CHANNEL
 - PMHSP_CHANNEL
 - acpitabl/PMHSP_CHANNEL
 - MHSP_CHANNEL
 - acpitabl/MHSP_CHANNEL
dev_langs:
 - c++
helpviewer_keywords:
 - _MHSP_CHANNEL
---

## -description

This topic describes the **MHSP_CHANNEL** structure used by the Microsoft HSP ACPI table.

## -struct-fields

### -field ChannelBaseAddress

Defines the **UINT64** member **ChannelBaseAddress**.

### -field RequestDoorbellAddress

Defines the **UINT64** member **RequestDoorbellAddress**.

### -field ReplyDoorbellAddress

Defines the **UINT64** member **ReplyDoorbellAddress**.

### -field ChannelSize

Defines the **UINT32** member **ChannelSize**.

### -field IrqResource

Defines the **UINT32** member **IrqResource**.

### -field ChannelParameters

Defines the **UINT32** member **ChannelParameters**.

## -remarks

## -see-also
