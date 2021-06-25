---
UID: NE:dot11wificxtypes._WDI_SCAN_TYPE
tech.root: netvista
title: WDI_SCAN_TYPE (dot11wificxtypes.h)
ms.date: 06/23/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_SCAN_TYPE enum defines scan types.
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
 - _WDI_SCAN_TYPE
 - WDI_SCAN_TYPE
f1_keywords:
 - _WDI_SCAN_TYPE
 - dot11wificxtypes/_WDI_SCAN_TYPE
 - WDI_SCAN_TYPE
 - dot11wificxtypes/WDI_SCAN_TYPE
dev_langs:
 - c++
---

## -description

The WDI_SCAN_TYPE enumeration defines scan types.

## -enum-fields

### -field WDI_SCAN_TYPE_ACTIVE_ONLY

The port should transmit a probe request on the channels that it scans. Even for active scans, the port must follow regulatory restrictions on the channel and must not scan on channels that would need a passive scan.

### -field WDI_SCAN_TYPE_PASSIVE_ONLY

The port should not transmit a probe request on the channels that it scans.

### -field WDI_SCAN_TYPE_AUTO

The port can perform an active or passive can or can use a combination of both scan types. It should prefer using Active scans when possible. This is the default scan type setting.

### -field WDI_SCAN_TYPE_MAX_VALUE

## -remarks

The **WDI_SCAN_TYPE** enum is a parameter of the [**WDI_TLV_SCAN_MODE**](/windows-hardware/drivers/netcx/wdi-tlv-scan-mode) TLV.

## -see-also

[**WDI_TLV_SCAN_MODE**](/windows-hardware/drivers/netcx/wdi-tlv-scan-mode)