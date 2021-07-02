---
UID: NE:dot11wificxtypes._WDI_DISABLE_DATA_PATH_OFFLOADS_SCENARIO
tech.root: netvista
title: WDI_DISABLE_DATA_PATH_OFFLOADS_SCENARIO (dot11wificxtypes.h)
ms.date: 06/30/2021
targetos: Windows
description: 
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: 
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
 - _WDI_DISABLE_DATA_PATH_OFFLOADS_SCENARIO
 - WDI_DISABLE_DATA_PATH_OFFLOADS_SCENARIO
f1_keywords:
 - _WDI_DISABLE_DATA_PATH_OFFLOADS_SCENARIO
 - dot11wificxtypes/_WDI_DISABLE_DATA_PATH_OFFLOADS_SCENARIO
 - WDI_DISABLE_DATA_PATH_OFFLOADS_SCENARIO
 - dot11wificxtypes/WDI_DISABLE_DATA_PATH_OFFLOADS_SCENARIO
dev_langs:
 - c++
---

## -description

## -enum-fields

### -field WDI_DISABLE_DATA_PATH_OFFLOADS_SCENARIO_NONE

This is the default scenario and indicates that offloads should not be disabled.

### -field WDI_DISABLE_DATA_PATH_OFFLOADS_SCENARIO_ENCRYPTION_CONNECTION

Indicates that the IHV may need to perform encryption/decryption operations on packets in software instead of hardware and therefore can’t enable offloads.

### -field WDI_DISABLE_DATA_PATH_OFFLOADS_SCENARIO_HARDWARE_ERROR

Indicates that the IHV has encountered a hardware error that is preventing supported offloads from being enabled.

## -remarks

The **WDI_BAND_ID** enum is used in the payload buffer of the [**WDI_TLV_ASSOCIATION_RESULT_PARAMETERS**](/windows-hardware/drivers/netcx/wdi-tlv-association-result-parameters) TLV.

## -see-also

[**WDI_TLV_ASSOCIATION_RESULT_PARAMETERS**](/windows-hardware/drivers/netcx/wdi-tlv-association-result-parameters)