---
UID: NE:dot11wificxtypes._WDI_FTM_BANDWIDTH
tech.root: netvista
<<<<<<< HEAD
title: WDI_FTM_BANDWIDTH (dot11wificxtypes.h)
ms.date: 07/19/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_FTM_BANDWIDTH enum defines the negotiated bandwidth between two STAs to exercise the FTM.
=======
title: WDI_FTM_BANDWIDTH
ms.date: 04/30/2021
targetos: Windows
description: "Microsoft reserves the WDI_FTM_BANDWIDTH enumeration for internal use only. Don't use this enumeration in your code."
>>>>>>> main
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
<<<<<<< HEAD
req.target-min-winverclnt: Windows 11 
=======
req.target-min-winverclnt: Windows 11Windows 11
>>>>>>> main
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

### -field WDI_FTM_BANDWIDTH_5

5 MHz.

### -field WDI_FTM_BANDWIDTH_10

10 MHz.

### -field WDI_FTM_BANDWIDTH_20

20 MHz.

### -field WDI_FTM_BANDWIDTH_40

40 MHz.

### -field WDI_FTM_BANDWIDTH_80

80 MHz.

### -field WDI_FTM_BANDWIDTH_80_80

80+80 MHz.

### -field WDI_FTM_BANDWIDTH_160

160 MHz.

### -field WDI_FTM_BANDWIDTH_2160

2160 MHz.

## -remarks

The **WDI_FTM_BANDWIDTH** enum is a value in the [**WDI_TLV_FTM_RESPONSE**](/windows-hardware/drivers/netcx/wdi-tlv-ftm-response) TLV.

## -see-also

[**WDI_TLV_FTM_RESPONSE**](/windows-hardware/drivers/netcx/wdi-tlv-ftm-response)