---
UID: NE:dot11wificxtypes._WDI_FTM_PROPAGATION
tech.root: netvista
title: WDI_FTM_PROPAGATION (dot11wificxtypes.h)
ms.date: 07/19/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_FTM_PROPAGATION enum defines the propagation properties of a signal tat are estimated by the LE's logic.
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
 - _WDI_FTM_PROPAGATION
 - WDI_FTM_PROPAGATION
f1_keywords:
 - _WDI_FTM_PROPAGATION
 - dot11wificxtypes/_WDI_FTM_PROPAGATION
 - WDI_FTM_PROPAGATION
 - dot11wificxtypes/WDI_FTM_PROPAGATION
dev_langs:
 - c++
---

## -description

The **WDI_FTM_PROPAGATION** enumeration defines the propagation properties of a signal that are estimated by the LE's logic.

## -enum-fields

### -field WDI_FTM_PROPAGATION_UNKNOWN:0

The default value. Nothing is assumed about how the signal was propagated, so the value should not have an effect on how the measurement is treated. This is the same as if the propagation field is not provided.

### -field WDI_FTM_PROPAGATION_INDIRECT_PATH:1

The LE estimated a low confidence measurement due to the detection of the transmission occurring through a Non-Line of Sight without a direct path or the transmission was too low to be properly received. It is assumed the measurement occurred mostly using a reflected signal, so it should not be as trusted as much as other measurements. This could be used as a guidance for upper layers to deprioritize or not use this measurement, so it is important for the detection logic to avoid false positives. False negatives are less problematic but are not desirable.

### -field WDI_FTM_PROPAGATION_LINE_OF_SIGHT:2

The LE estimated a high accurate measurement due to the detection of the transmission occurring in a Line of Sight with a strong direct path. It is assumed that the measurement occurred without intervening obstacles, so it should be a preferred measurement. This could be used as a guidance for upper layers to prioritize this measurement, so it is important for the detection logic to avoid false positives. False negatives are less problematic but are not desirable.

## -remarks

The **WDI_FTM_BANDWIDTH** enum is a value in the [**WDI_TLV_FTM_RESPONSE**](/windows-hardware/drivers/netcx/wdi-tlv-ftm-response) TLV.

## -see-also

[**WDI_TLV_FTM_RESPONSE**](/windows-hardware/drivers/netcx/wdi-tlv-ftm-response)