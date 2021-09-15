---
UID: NE:dot11wificxtypes._WDI_FTM_BANDWIDTH
tech.root: netvista
title: WDI_FTM_BANDWIDTH (dot11wificxtypes.h)
ms.date: 09/15/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_FTM_BANDWIDTH enum defines the negotiated bandwidth between two STAs to exercise the FTM.
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
 - _WDI_FTM_BANDWIDTH
 - WDI_FTM_BANDWIDTH
f1_keywords:
 - _WDI_FTM_BANDWIDTH
 - dot11wificxtypes/_WDI_FTM_BANDWIDTH
 - WDI_FTM_BANDWIDTH
 - dot11wificxtypes/WDI_FTM_BANDWIDTH
dev_langs:
 - c++
---

## -description

The **WDI_FTM_BANDWIDTH** enumeration defines the negotiated bandwidth between two STAs to exercise the Fine Timing Measurement (FTM).


## -enum-fields

### -field WDI_FTM_BANDWIDTH_5:1

5 MHz.

### -field WDI_FTM_BANDWIDTH_10:2

10 MHz.

### -field WDI_FTM_BANDWIDTH_20:3

20 MHz.

### -field WDI_FTM_BANDWIDTH_40:4

40 MHz.

### -field WDI_FTM_BANDWIDTH_80:5

80 MHz.

### -field WDI_FTM_BANDWIDTH_80_80:6

80+80 MHz.

### -field WDI_FTM_BANDWIDTH_160:7

160 MHz.

### -field WDI_FTM_BANDWIDTH_2160:8

2160 MHz.

## -remarks

The **WDI_FTM_BANDWIDTH** enum is a value in the [**WDI_TLV_FTM_RESPONSE**](/windows-hardware/drivers/netcx/wdi-tlv-ftm-response) TLV.

## -see-also

[**WDI_TLV_FTM_RESPONSE**](/windows-hardware/drivers/netcx/wdi-tlv-ftm-response)