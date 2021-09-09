---
UID: NE:dot11wificxtypes._WDI_BSS_SELECTION_FLAGS
tech.root: netvista
title: WDI_BSS_SELECTION_FLAGS (dot11wificxtypes.h)
ms.date: 06/30/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_BSS_SELECTION_FLAGS enum defines flags for BSS selection.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxtypes.h
api_name:
 - _WDI_BSS_SELECTION_FLAGS
 - WDI_BSS_SELECTION_FLAGS
f1_keywords:
 - _WDI_BSS_SELECTION_FLAGS
 - dot11wificxtypes/_WDI_BSS_SELECTION_FLAGS
 - WDI_BSS_SELECTION_FLAGS
 - dot11wificxtypes/WDI_BSS_SELECTION_FLAGS
dev_langs:
 - c++
---

## -description

The **WDI_BSS_SELECTION_FLAGS** enumeration defines flags for BSS selection.


## -enum-fields

### -field WDI_BSS_SELECTION_HOST_PREFERRED

Set for BSS entries that the host prefers to connect to. Non-preferred BSS entries would also be provided to the port, but should only be used  for connection if port performs its own BSS ranking.

### -field WDI_BSS_SELECTION_RECENT_ASSOCIATION_ERROR

Set for BSS entries that had recent association failures or were recently disassociated from. This flag is already accounted for by the host when setting WDI_BSS_SELECTION_HOST_PREFERRED.

### -field WDI_BSS_SELECTION_FLAGS_AP_REQUESTED_TRANSITION

Specifies whether this roam was requested by the AP or not (11v BSS Transition management request).

## -remarks

The **WDI_TLV_BSS_SELECTION_PARAMETERS** enum is a value in the [WDI_TLV_BSS_SELECTION_PARAMETERS](/windows-hardware/drivers/network/wdi-tlv-bss-selection-parameters) TLV.

## -see-also

[WDI_TLV_BSS_SELECTION_PARAMETERS](/windows-hardware/drivers/network/wdi-tlv-bss-selection-parameters)